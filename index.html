<!DOCTYPE html>
<html lang="cs">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Formulář pro nákup</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 50px;
        }
        form {
            max-width: 400px;
            margin: auto;
            background-color: #40E0D0; /* Světle tyrkysové pozadí */
            padding: 20px;
            border-radius: 10px;
            color: black;
        }
        label {
            display: block;
            margin: 10px 0 5px;
        }
        input[type="text"],
        input[type="email"],
        input[type="number"],
        select {
            width: 100%;
            padding: 8px;
            margin: 5px 0 10px;
            box-sizing: border-box;
        }
        input[type="submit"] {
            padding: 10px 20px;
            background-color: #555555; /* Tmavě šedé pozadí */
            color: white;
            border: none;
            cursor: pointer;
        }
        input[type="submit"]:hover {
            background-color: #444444; /* Tmavší šedé pozadí při najetí myší */
        }
        .error {
            color: red;
            font-size: 0.9em;
        }
        .recap {
            text-align: center;
            font-size: 2em; /* Dvojnásobná velikost písma */
            margin-top: 50px;
        }
        .recap-container {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
        }
        /* Odstranění šipek pro input type number */
        input[type=number]::-webkit-inner-spin-button,
        input[type=number]::-webkit-outer-spin-button {
            -webkit-appearance: none;
            margin: 0;
        }
        input[type=number] {
            -moz-appearance: textfield;
        }
    </style>
    <script>
        function updateTotalPrice() {
            const price = parseFloat(document.getElementById('price').value) || 0;
            const quantity = parseInt(document.getElementById('quantity').value) || 0;
            const total = price * quantity;
            document.getElementById('total').textContent = formatCurrency(total) + ' Kč';
        }

        function validateForm() {
            let valid = true;

            const name = document.getElementById('name').value.trim();
            if (name === "" || name.length > 50) {
                showError('nameError', 'Jméno je povinné a maximálně 50 znaků.');
                valid = false;
            } else {
                hideError('nameError');
            }

            const surname = document.getElementById('surname').value.trim();
            if (surname === "" || surname.length > 50) {
                showError('surnameError', 'Příjmení je povinné a maximálně 50 znaků.');
                valid = false;
            } else {
                hideError('surnameError');
            }

            const email = document.getElementById('email').value.trim();
            const emailPattern = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
            if (email === "" || !emailPattern.test(email) || email.length > 50) {
                showError('emailError', 'Zadejte platný email (maximálně 50 znaků).');
                valid = false;
            } else {
                hideError('emailError');
            }

            const street = document.getElementById('street').value.trim();
            if (street === "" || street.length > 50) {
                showError('streetError', 'Ulice je povinná a maximálně 50 znaků.');
                valid = false;
            } else {
                hideError('streetError');
            }

            const city = document.getElementById('city').value.trim();
            if (city === "" || city.length > 50) {
                showError('cityError', 'Město je povinné a maximálně 50 znaků.');
                valid = false;
            } else {
                hideError('cityError');
            }

            const postalCode = document.getElementById('postalCode').value.trim();
            if (postalCode === "" || postalCode.length !== 5 || isNaN(postalCode)) {
                showError('postalCodeError', 'PSČ je povinné a musí mít přesně 5 číslic.');
                valid = false;
            } else {
                hideError('postalCodeError');
            }

            const product = document.getElementById('product').value.trim();
            if (product === "") {
                showError('productError', 'Produkt je povinný.');
                valid = false;
            } else {
                hideError('productError');
            }

            const price = parseFloat(document.getElementById('price').value);
            if (isNaN(price) || price <= 0) {
                showError('priceError', 'Cena musí být kladné číslo.');
                valid = false;
            } else {
                hideError('priceError');
            }

            const quantity = parseInt(document.getElementById('quantity').value);
            if (isNaN(quantity) || quantity <= 0 || quantity > 20) {
                showError('quantityError', 'Počet kusů musí být kladné číslo a maximálně 20.');
                valid = false;
            } else {
                hideError('quantityError');
            }

            return valid;
        }

        function showError(id, message) {
            document.getElementById(id).textContent = message;
        }

        function hideError(id) {
            document.getElementById(id).textContent = '';
        }

        async function submitForm(event) {
            event.preventDefault();
            if (!validateForm()) return;

            const name = document.getElementById('name').value.trim();
            const surname = document.getElementById('surname').value.trim();
            const email = document.getElementById('email').value.trim();
            const street = document.getElementById('street').value.trim();
            const city = document.getElementById('city').value.trim();
            const postalCode = document.getElementById('postalCode').value.trim();
            const product = document.getElementById('product').value.trim();
            const price = parseFloat(document.getElementById('price').value);
            const quantity = parseInt(document.getElementById('quantity').value);
            const totalWithoutVat = (price * quantity) / 1.21;
            const totalWithVat = totalWithoutVat * 1.21;

            const currency = document.getElementById('currency').value;
            let rate = 1;

            try {
                const response = await fetch(`https://api.exchangerate-api.com/v4/latest/CZK`);
                const data = await response.json();
                rate = data.rates[currency] || 1;
            } catch (error) {
                console.error('Nepodařilo se načíst kurzovní lístek', error);
            }

            const totalInCurrency = (totalWithVat * rate).toFixed(2);

            const recapHTML = `
                <div class="recap">
                    <h2>Rekapitulace objednávky</h2>
                    <p><strong>Jméno:</strong> ${name}</p>
                    <p><strong>Příjmení:</strong> ${surname}</p>
                    <p><strong>Email:</strong> ${email}</p>
                    <p><strong>Ulice:</strong> ${street}</p>
                    <p><strong>Město:</strong> ${city}</p>
                    <p><strong>PSČ:</strong> ${postalCode}</p>
                    <p><strong>Produkt:</strong> ${product}</p>
                    <p><strong>Počet kusů:</strong> ${quantity}</p>
                    <p><strong>Celková cena bez DPH:</strong> ${formatCurrency(totalWithoutVat)} Kč</p>
                    <p><strong>Celková cena s DPH:</strong> ${formatCurrency(totalWithVat)} Kč</p>
                    <p><strong>Celková cena s DPH v ${currency}:</strong> ${totalInCurrency} ${currency}</p>
                </div>
            `;

            const newWindow = window.open('', '_blank');
            newWindow.document.write(`<html><head><title>Rekapitulace objednávky</title><style>body { display: flex; justify-content: center; align-items: center; height: 100vh; }</style></head><body>${recapHTML}</body></html>`);
            newWindow.document.close();
        }

        function formatCurrency(value) {
            return value.toFixed(2).replace(/\B(?=(\d{3})+(?!\d))/g, ' ');
        }

        function updatePrice() {
            const product = document.getElementById('product').value;
            const priceInput = document.getElementById('price');
            if (product === "Tričko") {
                priceInput.value = 499;
            } else {
                priceInput.value = 0;
            }
            updateTotalPrice();
        }
    </script>
</head>
<body>

<h2 style="text-align:center;">Formulář pro nákup</h2>

<form onsubmit="submitForm(event)">
    <label for="name">Jméno:</label>
    <input type="text" id="name" name="name" required maxlength="50">
    <div id="nameError" class="error"></div>

    <label for="surname">Příjmení:</label>
    <input type="text" id="surname" name="surname" required maxlength="50">
    <div id="surnameError" class="error"></div>

    <label for="email">Email:</label>
    <input type="email" id="email" name="email" required maxlength="50">
    <div id="emailError" class="error"></div>

    <label for="street">Ulice:</label>
    <input type="text" id="street" name="street" required maxlength="50">
    <div id="streetError" class="error"></div>

    <label for="city">Město:</label>
    <input type="text" id="city" name="city" required maxlength="50">
    <div id="cityError" class="error"></div>

    <label for="postalCode">PSČ:</label>
    <input type="text" id="postalCode" name="postalCode" required maxlength="5" minlength="5" pattern="\d{5}">
    <div id="postalCodeError" class="error"></div>

    <label for="product">Produkt:</label>
    <select id="product" name="product" required onchange="updatePrice()">
        <option value="">--Vyberte produkt--</option>
        <option value="Tričko">Tričko</option>
    </select>
    <div id="productError" class="error"></div>

    <label for="price">Cena za kus (včetně DPH):</label>
    <input type="number" id="price" name="price" readonly>
    <div id="priceError" class="error"></div>

    <label for="quantity">Počet kusů:</label>
    <input type="number" id="quantity" name="quantity" value="1" min="1" max="20" required oninput="updateTotalPrice()">
    <div id="quantityError" class="error"></div>

    <p>Celková cena včetně DPH: <span id="total">0.00 Kč</span></p>

    <label for="currency">Celkovou cenu v Kč přepočti na vybranou měnu:</label>
    <select id="currency" name="currency">
        <option value="USD">USD</option>
        <option value="EUR">EUR</option>
        <option value="GBP">GBP</option>
        <option value="CHF">CHF</option>
        <option value="JPY">JPY</option>
        <!-- Další měny -->
    </select>

    <input type="submit" value="Odeslat objednávku">
</form>

</body>
</html>
