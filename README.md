
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>UPI QR Code Generator</title>
	
    <meta name="description" content="Generate UPI QR Codes instantly with this free UPI QR Code Generator. Simplify payments for businesses and individuals.">

    <script src="https://cdnjs.cloudflare.com/ajax/libs/qrcodejs/1.0.0/qrcode.min.js"></script>
    <script src="https://code.jquery.com/jquery-3.6.0.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/html2canvas/1.3.2/html2canvas.min.js"></script>
    <style>
   html.lenis {
  height: auto;
}
.lenis.lenis-smooth {
  scroll-behavior: auto;
}
.lenis.lenis-smooth [data-lenis-prevent] {
  overscroll-behavior: contain;
}
.lenis.lenis-stopped {
  overflow: hidden;
}

.blue_text_span {
    background: linear-gradient(
    to right,
    #006aff 20%,
    #BFCFE7 37%,
    #BFCFE7 40%,
    #006aff 70%
  );
    -webkit-background-clip: text;
    background-clip: text;
    -webkit-text-fill-color: transparent;
    text-fill-color: transparent;
    background-size: 500% auto;
    animation: textShine 3s ease-in-out infinite alternate;
}

#ifsc_form {
    display: inline-block !important;
    width: 100%;
}

@keyframes textShine {
  0% {
    background-position: 0% 20%;
  }
  50% {
    background-position: 50% 50%;
  }
  100% {
    background-position: 100% 50%;
  }
}


.hidden {
    display: none;
}

#result {
  color: #006aff;
  font-size: 16px;
  text-transform: capitalize;
  font-family: "Inter", sans-serif;
  width: 100%;
}

.ifsc_show_card {
  display: flex;
  flex-direction: row;
  align-items: flex-start;
  background: #f0f1f2;
  border-radius: 12px;
  overflow: hidden;
  width: 100%;
  gap: 15px;
  padding: 15px;
}

.ifsc_show_card .ifsc_header {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  justify-content: space-between;
  width: 60%;
  gap: 20px;
  padding: 20px 20px;
  min-height: 288px;
  border-radius: 12px;
  background: #fff;
}

.ifsc_show_card .ifsc_body {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  justify-content: space-between;
  width: 40%;
  gap: 20px;
  padding: 20px 20px;
  min-height: 288px;
  border-radius: 12px;
  background: #fff;
}

.ifsc_show_card .ifsc_footer {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
  width: 100%;
  padding: 0px 20px;
  padding-bottom: 20px;
}

.ifsc_show_card h6 {
  font-size: 15px;
  color: #006aff;
  margin: 0;
  font-weight: 500;
  text-transform: uppercase;
  font-family: "Inter", sans-serif;
}

.ifsc_show_card h2 {
  font-size: 18px;
  color: #222;
  font-weight: 600;
  font-family: "Inter", sans-serif;
  margin: 0;
}

.ifsc_show_card span {
  width: 100%;
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  gap: 7px;
  border-bottom: 1px solid #0000000d;
  padding-bottom: 15px;
}

.ifsc_show_card span:last-child {
  border: none;
}

/* .ifsc_show_card .ifsc_body span {
  border-color: #fff;
} */


.quick-info::after {
    content: '';
    position: absolute;
    bottom: 0;
    left: 0;
    width: 100%;
    height: 15%;
    background: linear-gradient(#0062ff00 30%,#0062ff);
    z-index: 9999;
    opacity: 0.4;
}

.box-interior {
    background: #f2f2f57d;
    backdrop-filter: blur(60px);
    border: 1px solid #ffffff8c;
}

.show_struck_1 {
    animation: scaleUp 0.6s; /* Adjust '2s' to control the duration of the animation */
}

.show_struck_2 {
    animation: scaleUp 0.8s; /* Adjust '2s' to control the duration of the animation */
}

@keyframes scaleUp {
    from { transform: scale(0.5); }
    to { transform: scale(1); }
}

@keyframes fadeIn {
    from { opacity: 0; }
    to { opacity: 1; }
}

/*
.gstinfo {
	overflow-y:scroll;
}
.gstinfo::-webkit-scrollbar {
  width: 2px;
}
.gstinfo::-webkit-scrollbar-track {
  background: #f1f1f1; 
}
.gstinfo::-webkit-scrollbar-thumb {
  background: #0069ff; 
}
.gstinfo::-webkit-scrollbar-thumb:hover {
  background: #0069ff; 
}
*/

.collection-item-change {
    position: relative;
}

.main_ul_sticky li.artwork {
    display: none;
    transition: 0.3s;
}

.main_ul_sticky li.artwork.active {
    display: inline-block;
}

.magic_card {
    box-shadow: 0 0 #0000, 0 0 #0000, 0px 1px 0px 0px hsla(0,0%,100%,.06) inset, 0px 4px 10px 0px rgba(0,0,0,.3) !important;
}

.collection-list .collection-item-change::after {
    content: '';
    position: absolute;
    left: 25px;
    height: 100%;
    width: 1px;
    background: #00000014;
    top: 50px;
}


.glowing-wrapper-button {
   
}

.changelog_link_last svg.change_main {
    color: #0069ff;
    transition: 0.3s;
}

.changelog_link_last:hover .star {
    background: #006aff;
    color: #fff;
}

.changelog_link_last:hover svg.change_main {
    color: #fff;
}

.star path.path-2 {
    stroke: #0069ff;
}

.collection-item-change:hover .star {
    background: #006aff;
    color: #fff;
}

.collection-item-change:hover .star path.path-2 {
    stroke: #fff;
}

.star {
    color: #006aff;
    transition: 0.3s;
}

.bg-inverse {
  background-color: #FFFFFF !important;
}

.bg-primary {
  background-color: #000000 !important;
}

@keyframes textShine {
    0% {
        background-position: 0% 50%;
    }
    100% {
        background-position: 100% 50%;
    }
}

li.feature .product {
		height: 0px;
    overflow: hidden;
}
li.feature.active .product {
		height: auto;
}
.main_ul_sticky {
    padding-left: 0;
    height: 100%;
    display: flex;
    flex-direction: column;
    justify-content: flex-start;
}
.progressbar-background {
    background: linear-gradient(rgb(0 106 255) 0%, rgb(87, 87, 92) 36.0685%, rgb(87, 87, 92) 100%);
    height: 50vh;
    width: 1px;
}
#progress-bar {
    width: 1px;
    height: var(--y);
    background: rgb(0 106 255);
    z-index: 100;
    transition: width 0.3s ease;
    position: relative;
    max-height: 100%;
}
#progress-bar::after {
    content: "";
    background-color: #fff;
    border-radius: 100%;
    width: 6px;
    height: 6px;
    position: absolute;
    left: 50%;
    bottom: 0;
    translate: -4px 0px;
    border: 4px solid #006aff;
}
.line {
	position:relative;
}

.line-mask {
	position: absolute;
  top:0;
	right:0;
  background-color:#fff;
  opacity:0.65;
  width:100%;
  height:100%;
  z-index:2;
}

.blur{
  	pointer-events: none;
  }
  
  a.changelog_link_last.w-inline-block:hover .change_main-copy {
    color: #fff;
}

a.changelog_link_last.w-inline-block .change_main-copy {
    color: #006aff;
}


#banner.upi .tool_box {
    display: flex;
    flex-direction: row;
    align-items: stretch;
    gap: 20px;
    width: 100%;
    justify-content: space-between;
    max-width: 100%;
}

#banner.upi .tool_box form input {
  width: 100%;
  display: inline-block;
  height: 60px;
  border: 1px solid #f0f1f2;
  border-radius: 10px;
  padding: 20px 20px;
  font-size: 15px;
  outline: none;
  background: #f0f1f2;
}

#banner.upi .tool_box form label {
  font-size: 16px;
  font-weight: 500;
  color: #000;
  margin-bottom: 10px;
}

#banner.upi .tool_box form button#submit-btn {
  position: absolute;
  top: 8px;
  right: 8px;
  background-color: #006aff !important;
  font-size: 14px;
  white-space: nowrap;
  font-family: "Poppins", sans-serif;
  color: #fff !important;
  border: none;
  padding: 13px 20px;
  line-height: 18px;
  display: flex;
  align-items: center;
  overflow: hidden;
  border-radius: 0px;
  text-transform: capitalize;
  font-weight: 400;
  border-radius: 6px !important;
  gap: 8px;
  transition: 0.3s;
}

#banner.upi .tool_box .field_details {
  width: 55%;
  height: 100%;
}

#banner.upi .tool_box .qrshowcase {
  width: 430px;
  max-width: 430px;
}

#banner.upi .tool_box .qrshowcase ul {
  padding: 0;
  margin: 0;
  display: flex;
  align-items: center;
  flex-direction: row;
  justify-content: center;
  margin-top: 20px;
  gap: 15px;
  flex-wrap: wrap;
  width: 78%;
}

#banner.upi .tool_box .qrshowcase ul li {
  display: flex;
  width: 116px;
  /* height: 35px; */
  flex-direction: row;
  align-items: center;
  justify-content: center;
}

#banner.upi .tool_box .qrshowcase ul li img {
  width: 100%;
  height: 24px;
  object-fit: contain;
}

#banner.upi .tool_box .qrshowcase ul.four_lg li {
  width: auto;
  height: 24px;
  overflow: hidden;
}

#banner.upi .tool_box .qrshowcase .whit_card {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: space-around;
  height: 100%;
  box-shadow: 0 0 #0000,0 0 #0000,var(--tw-shadow);
  --tw-shadow: 0 10px 15px -3px rgba(0,0,0,.1),0 4px 6px -4px rgba(0,0,0,.1);
  background-color: #fff;
  border: 1px solid rgba(32, 32, 32, 0.1);
  border-radius: 12px;
  padding: 2vw 0;
  gap: 10px;
}

#banner.upi .tool_box .qrshowcase .whit_card div#display-payee-name {
  font-size: 20px;
  color: #222;
  font-weight: 600;
  font-family: "Inter", sans-serif;
  margin: 0;
  margin-bottom: 0;
}

#banner.upi .tool_box .qrshowcase .whit_card h3 {
  font-size: 18px;
  color: #222;
  font-weight: 600;
  font-family: "Inter", sans-serif;
  margin: 0;
  margin-bottom: 10px;
}

#banner.upi .tool_box form#qr-generator-form .form-group {
  width: 100%;
  font-family: "Inter", sans-serif;
}

#banner.upi .tool_box form#qr-generator-form select#payment-type {
  width: 100%;
  display: inline-block;
  height: 55px;
  border: 1px solid #f0f1f2;
  border-radius: 10px;
  padding: 0px 20px;
  font-size: 18px;
  outline: none;
  background: #f0f1f2;
}

#banner.upi .tool_box #bank-input-group span input#account-input {
    margin-bottom: 10px;
}

#banner.upi .tool_box form#qr-generator-form textarea {
  display: flex;
  width: 100%;
  height: 100px;
  border: 1px solid #f0f1f2;
  border-radius: 10px;
  padding: 20px 20px;
  font-size: 18px;
  outline: none;
  background: #f0f1f2;
  resize: none;
  font-family: "Inter", sans-serif;
}

#banner.upi .tool_box form#qr-generator-form button {
  background-color: #006aff !important;
  font-size: 14px;
  white-space: nowrap;
  font-family: "Poppins", sans-serif;
  color: #fff !important;
  border: none;
  padding: 13px 20px;
  line-height: 18px;
  display: flex;
  align-items: center;
  overflow: hidden;
  border-radius: 0px;
  text-transform: capitalize;
  font-weight: 400;
  border-radius: 6px !important;
  gap: 8px;
  transition: 0.3s;
}

#banner.upi .tool_box form {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  width: 100%;
  position: relative;
  gap: 15px;
}

#banner.upi .tool_box .qrshowcase .whit_card span {
  display: flex;
  flex-direction: column;
  align-items: center;
}

#banner.upi .tool_box .qrshowcase .whit_card span div#qrcode {
  margin-bottom: 20px;
}

#banner.upi .tool_box .qrshowcase .whit_card span div#display-vpa {
  margin-bottom: 20px;
}

#banner.upi .tool_box form button {
  width: 100%;
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: center;
  padding: 16px 20px;
}

@media only screen and (max-width:767px) {

    .tools_banner {
        padding-top: 110px;
        /* background: #006aff; */
        background: #000 url(../img/notification_bg.png) 50% 100%;
        padding-bottom: 4vw;
    }

    section.tools_list {
        padding: 20px 15px;
    }

    .tools_list .tools_list_item {
        height: auto;
        margin-bottom: 20px;
    }

    .tools_banner h2 {
        margin: 0;
        font-size: 29px;
    }

    #banner.upi .tool_box {
        display: flex;
        flex-direction: column;
        align-items: stretch;
        gap: 20px;
        width: 100%;
        justify-content: space-between;
    }

    #banner.upi .tool_box .field_details {
        width: 100%;
        height: 100%;
    }

    #banner.upi .tool_box .qrshowcase {
        width: 100%;
        max-width: 100%;
    }

    #banner.upi .tool_box .qrshowcase .whit_card h3 {
        font-size: 14px;
        text-align: center;
    }

    #banner.upi .tool_box .qrshowcase .whit_card div#display-payee-name {
        font-size: 20px;
        margin: 20px 0px;
    }

    #banner.upi .tool_box .qrshowcase ul {
        width: 100%;
    }

    #banner.upi .tool_box .qrshowcase .whit_card {
        padding-bottom: 30px;
    }

    .navbar-expand-lg .navbar-nav .nav-link.dropdown-toggle.show,
    .navbar-expand-lg .navbar-nav .nav-link.dropdown-toggle {
        justify-content: center;
    }

    #banner.sip_cal .inner_banner_side {
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: space-between;
        gap: 30px;
        padding: 25px 25px !important;
    }

    #banner.sip_cal .inner_banner_side .text_side {
        display: flex;
        flex-direction: column;
        align-items: center;
        text-align: left;
    }

    #banner.sip_cal .inner_banner_side .text_side p.animate__animated.animate__fadeInUp {
        text-align: center;
        margin-bottom: 0;
    }

    .free_tool_ifsc .inner_banner_side p.animate__animated.animate__fadeInUp {
        padding: 0 20px;
        font-size: 16px;
    }

    #banner.sip_cal .inner_banner_side .tool_box {
        width: 80vw;
        background: #fff;
        border-radius: 25px;
    }

    .inner_banner_side .tool_box form#sip-calculator .inamount input[type="number"] {
        width: 100px;
    }
    
    .html-embed-2 {
    width: 91%;
}
  }
  @media only screen and (min-width:768px) and (max-width:991px) {

    .tools_list .tools_list_item .tools_list_item_content p {
        font-size: 16px;
        margin-top: 10px;
        min-height: 112px;
    }

    #banner.upi .tool_box {
        display: flex;
        flex-direction: row;
        align-items: stretch;
        gap: 20px;
        width: 80vw;
        justify-content: space-between;
    }

    #banner.upi .tool_box .field_details {
        width: 100%;
        height: 100%;
    }
    
    #banner.upi .tool_box form#qr-generator-form {
        width: 100%;
    }

    #banner.upi .tool_box .qrshowcase {
        width: 125%;
        max-width: 125%;
    }

    #banner.upi .tool_box .qrshowcase .whit_card h3 {
        font-size: 14px;
        text-align: center;
    }

    #banner.upi .tool_box .qrshowcase .whit_card div#display-payee-name {
        font-size: 20px;
        margin: 20px 0px;
    }

    #banner.upi .tool_box .qrshowcase ul {
        width: 100%;
    }

    #banner.upi .tool_box .qrshowcase .whit_card {
        padding-bottom: 30px;
    }

    #banner.sip_cal .inner_banner_side {
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: space-between;
        gap: 30px;
        padding: 25px 25px !important;
    }

    #banner.sip_cal .inner_banner_side .text_side {
        display: flex;
        flex-direction: column;
        align-items: center;
        text-align: left;
    }

    #banner.sip_cal .inner_banner_side .text_side p.animate__animated.animate__fadeInUp {
        text-align: center;
        margin-bottom: 0;
    }

    #banner.sip_cal .inner_banner_side .tool_box {
        width: 80vw;
        background: #fff;
        border-radius: 25px;
    }
    .html-embed-2 {
    width: 90%;
}
    }
@media only screen and (min-width:992px) and (max-width:1100px) {
    .html-embed-2 {
    width: 90%;
}
}

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

<BR>
 <p>The <strong>UPI QR Code Generator</strong> allows you to create quick and secure UPI QR codes for seamless digital payments. Ideal for businesses, freelancers, and individuals, this tool makes transactions easier and faster.</p>

<h2>Why Use a UPI QR Code Generator?</h2>
    <p>UPI QR codes simplify payments by allowing users to scan and pay instantly.</p>
    <p><strong>1. Instant Payment Processing:</strong> No need to manually enter UPI details.</p>
    <p><strong>2. Secure Transactions:</strong> Reduces the risk of entering incorrect details.</p>
    <p><strong>3. Useful for Businesses & Individuals:</strong> Ideal for shops, freelancers, and service providers.</p>
    <p><strong>4. Free & Easy to Use:</strong> Generate UPI QR codes instantly without any cost.</p>

<h2>How to Use the UPI QR Code Generator?</h2>
    <p><strong>Step 1:</strong> Enter your UPI ID or payment details.</p>
    <p><strong>Step 2:</strong> Specify the amount (optional).</p>
    <p><strong>Step 3:</strong> Click the "Generate QR Code" button.</p>
    <p><strong>Step 4:</strong> Download or share the QR code for quick payments.</p>

<h2>Conclusion</h2>
    <p>The <strong>UPI QR Code Generator</strong> is a fast and secure way to create payment QR codes for easy transactions. Whether you are a business owner or an individual, this tool simplifies the payment process.</p>

