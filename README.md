# Currency Converter

A simple and responsive Currency Converter web application built with HTML, CSS, and JavaScript, using the ExchangeRate API to fetch real-time currency rates.

## Features

Fetches live currency exchange rates

Auto-generated currency lists using <datalist>

Converts any amount between any two supported currencies

Clean and responsive interface

Lightweight and vanilla JavaScript only

##  Project Structure
 Currency-Converter
 ├── index.html
 ├── style.css
 ├── script.js
 └── README.md

## Technologies Used

HTML5

CSS3

JavaScript (Fetch API)

ExchangeRate API (v6)

## Setup & Usage
1. Get an API Key

Go to https://www.exchangerate-api.com/
 and sign up for a free API key.

2. Insert Your API Key

Open script.js and replace:

const api_key = "-------------------------";


with your actual key.

3. Run the Project

Simply open index.html in any browser.

## Code Overview
### Fetch Supported Currency Codes
fetch(url + "/codes")
  .then(res => res.json())
  .then(data => {
      let options = "";
      for (let item of data.supported_codes) {
          options += `<option value=${item[0]}>${item[1]}</option>`;
      }
      currency1.innerHTML = options;
      currency2.innerHTML = options;
  });

### Convert Currency
fetch(url + "/latest/" + money1)
  .then(res => res.json())
  .then(data => {
      const total = (data.conversion_rates[money2] * quantity).toFixed(3);
      result.classList.remove("passive");
      result.innerHTML = `${quantity} ${money1} = ${total} ${money2}`;
  });

## UI Preview

Input fields for selecting currencies

Amount field

Convert button

Result display box

## License

