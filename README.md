<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>UPI QR Code Generator</title>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/qrcodejs/1.0.0/qrcode.min.js"></script>
    <script src="https://code.jquery.com/jquery-3.6.0.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/html2canvas/1.3.2/html2canvas.min.js"></script>
    <style>
        /* Add your CSS styles here */
        /* ... (Include all the CSS styles provided in your question) ... */
    </style>
</head>
<body>
    <section id="banner" class="upi">
        <div class="tool_box">
            <div class="field_details">
                <form id="qr-generator-form">
                    <div class="form-group">
                        <label for="payee-name-input">Merchant / Payee Name:</label>
                        <input type="text" id="payee-name-input" placeholder="Enter Merchant / Payee Name" value="" />
                    </div>
                    <div class="form-group">
                        <label for="payment-type">Payment Address Type:</label>
                        <select id="payment-type">
                            <option value="upi">UPI Address</option>
                            <option value="bank">Bank Account Number</option>
                        </select>
                    </div>
                    <div class="form-group" id="upi-input-group">
                        <label for="vpa-input">Enter your UPI VPA:</label>
                        <input type="text" id="vpa-input" placeholder="example@upi" value="" />
                    </div>
                    <div class="form-group" id="bank-input-group" style="display: none;">
                        <span>
                            <label for="account-input">Enter your Bank Account Number:</label>
                            <input type="text" id="account-input" placeholder="Bank Account Number" />
                        </span>
                        <span>
                            <label for="ifsc-input">Enter IFSC Code:</label>
                            <input type="text" id="ifsc-input" placeholder="IFSC Code" />
                        </span>
                    </div>
                    <div class="form-group">
                        <label for="amount-input">Enter the fixed amount (in INR):</label>
                        <input type="number" id="amount-input" placeholder="Amount" step="0.01" min="0" aria-required="true" />
                    </div>
                    <div class="form-group">
                        <label for="notes-input">Description (Notes):</label>
                        <textarea id="notes-input" placeholder="Enter any notes here"></textarea>
                    </div>
                    <button type="button" id="download-btn"><iconify-icon icon="lucide:download"></iconify-icon> Download QR Code</button>
                </form>
            </div>
            <div id="qr-code-container" class="qrshowcase">
                <div class="whit_card">
                    <div id="display-payee-name"></div>
                    <span>
                        <div id="qrcode" aria-live="polite"></div>
                        <div id="display-vpa"></div>
                        <h3>Scan and pay with any BHIM UPI app</h3>
                    </span>
                    <span>
                        <ul class="two_lg">
                            <li><img src="https://cdn.prod.website-files.com/6566e447a5e4ff5036b1a994/662b32d1813cb922f3730e75_bhim-logo.png" alt="" /></li>
                            <li><img src="https://cdn.prod.website-files.com/6566e447a5e4ff5036b1a994/662b32d1ef15a171c2825ba5_upi-logo.png" alt="" /></li>
                        </ul>
                        <ul class="four_lg">
                            <li><img src="https://cdn.prod.website-files.com/6566e447a5e4ff5036b1a994/662b32d1904aefc612967e2b_gpay.svg" /></li>
                            <li><img src="https://cdn.prod.website-files.com/6566e447a5e4ff5036b1a994/662b32d0ccb07ec924d85d55_phonepay.svg" alt="" /></li>
                            <li><img src="https://cdn.prod.website-files.com/6566e447a5e4ff5036b1a994/662b351c48b2f2289e7f7867_paytm.svg" alt="" /></li>
                            <li><img src="https://cdn.prod.website-files.com/6566e447a5e4ff5036b1a994/662b32d16c6cfbca695921f4_amazonpay.png" alt="" /></li>
                            <li><img src="https://cdn.prod.website-files.com/6566e447a5e4ff5036b1a994/662b32d1ccb07ec924d85d85_OG_Lite_logo.png" alt="" /></li>
                        </ul>
                    </span>
                </div>
            </div>
        </div>
    </section>

    <script>
        "use strict";

        // Helper function to update display text
        function updateDisplayText(elementId, value, defaultValue) {
            document.getElementById(elementId).textContent = value ? value : defaultValue;
        }

        // Function to handle real-time QR code generation and updates
        function updateQRCode() {
            const qrCodeElement = document.getElementById("qrcode");
            const paymentType = document.getElementById("payment-type").value;
            const payeeName = document.getElementById("payee-name-input").value.trim();
            const vpa = document.getElementById("vpa-input").value.trim();
            const amount = document.getElementById("amount-input").value;
            const notes = document.getElementById("notes-input").value.trim();
            const accountNumber = document.getElementById('account-input').value;
            const ifscCode = document.getElementById('ifsc-input').value;
            qrCodeElement.innerHTML = ''; // Clear the previous QR code

            let url;
            if (paymentType === 'upi' && vpa && amount) {
                url = createUPIUrl(vpa, amount, payeeName, notes);
            } else if (paymentType === 'bank' && accountNumber && ifscCode) {
                url = generateBankUrl(accountNumber, ifscCode, amount, payeeName, notes);
            } else {
                url = 'https://unesync.com/'; // Placeholder URL when required fields are not filled
            }

            // Generate the QR code with the current URL or placeholder
            new QRCode(qrCodeElement, createQRCodeOptions(url));
        }

        // Function to create UPI URL
        function createUPIUrl(vpa, amount, payeeName, notes) {
            const baseUrl = "upi://pay";
            const encodedNotes = encodeURIComponent(notes); // Ensure the notes are URL encoded
            const queryParams = {
                pa: vpa,
                am: amount,
                cu: "INR",
                pn: payeeName,
                tn: encodedNotes // Use the encoded notes here
            };
            const queryString = new URLSearchParams(queryParams).toString();
            return `${baseUrl}?${queryString}`;
        }

        // Function to create Bank Account Number
        function generateBankUrl(accountNumber, ifscCode, amount, payeeName, notes) {
            const baseUrl = "upi://pay";
            const encodedPayeeName = encodeURIComponent(payeeName);
            const encodedNotes = encodeURIComponent(notes); // Ensure the notes are URL encoded
            const queryParams = {
                an: accountNumber,
                ifsc: ifscCode,
                am: amount,
                cu: "INR",
                pn: payeeName,
                tn: encodedNotes // Use the encoded notes here
            };
            return `${baseUrl}?pa=${accountNumber}@${ifscCode}.ifsc.npci&pn=${encodedPayeeName}&tn=${encodedNotes}&am=${encodeURIComponent(amount)}&cu=INR`;
        }

        // Function to create QR code options
        function createQRCodeOptions(text) {
            return {
                text: text,
                width: 200,
                height: 200,
                colorDark: "#000000",
                colorLight: "#ffffff",
                correctLevel: QRCode.CorrectLevel.H
            };
        }

        // Event listeners for input fields to update display text and QR code in real-time
        document.getElementById('payee-name-input').addEventListener('input', function() {
            updateDisplayText('display-payee-name', this.value, 'MERCHANT NAME');
            updateQRCode();
        });

        document.getElementById('vpa-input').addEventListener('input', function() {
            updateDisplayText('display-vpa', this.value, 'merchant@upi');
            updateQRCode();
        });

        document.getElementById('account-input').addEventListener('input', function() {
            updateDisplayText('display-vpa', this.value, 'merchant@upi');
            updateQRCode();
        });

        document.getElementById('amount-input').addEventListener('input', updateQRCode);
        document.getElementById('notes-input').addEventListener('input', updateQRCode);
        document.getElementById("payment-type").addEventListener('change', function() {
            updateQRCode(); // Update the QR code when the payment type changes
            // Show or hide relevant input groups
            document.getElementById("upi-input-group").style.display = this.value === "upi" ? "block" : "none";
            document.getElementById("bank-input-group").style.display = this.value === "bank" ? "block" : "none";
        });

        // Generate a placeholder QR code when the page loads
        document.addEventListener('DOMContentLoaded', updateQRCode);

        document.getElementById('display-payee-name').textContent = 'MERCHANT NAME';
        document.getElementById('display-vpa').textContent = 'merchant@upi';

        // Update display when 'Merchant / Payee Name' is entered
        document.getElementById('payee-name-input').addEventListener('input', function() {
            document.getElementById('display-payee-name').textContent = this.value.trim() ? this.value : 'MERCHANT NAME';
            updateQRCode();
        });

        // Update display when 'UPI ID' is entered
        document.getElementById('vpa-input').addEventListener('input', function() {
            document.getElementById('display-vpa').textContent = this.value.trim() ? this.value : 'merchant@upi';
            updateQRCode();
        });

        document.getElementById('account-input').addEventListener('input', function() {
            document.getElementById('display-vpa').textContent = this.value.trim() ? this.value : 'merchant@upi';
            updateQRCode();
        });

        document.getElementById('download-btn').addEventListener('click', function() {
            downloadQRCode();
        });

        function downloadQRCode() {
            const qrCodeContainer = document.getElementById('qr-code-container');

            if (!qrCodeContainer) {
                console.error('The QR code container element does not exist.');
                alert('The QR code container element does not exist.');
                return;
            }

            html2canvas(qrCodeContainer, {
                useCORS: true,
                logging: true,
                letterRendering: 1,
                scale: 2
            }).then(canvas => {
                const downloadLink = document.createElement('a');
                downloadLink.download = 'QRCode.png';
                // Use the Blob approach instead of data URL to handle potential size limitations
                canvas.toBlob(function(blob) {
                    const url = URL.createObjectURL(blob);
                    downloadLink.href = url;
                    downloadLink.click();
                    // Revoke the blob URL after the download
                    URL.revokeObjectURL(url);
                }, 'image/png');
            }).catch(err => {
                console.error('Error capturing QR code container:', err);
                alert('Failed to download QR code. See console for details.');
            });
        }
    </script>
</body>
</html>
