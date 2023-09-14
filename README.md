## Age Calculator

This is a simple age calculator that allows users to input their date of birth and calculate their age.

### How to use

1. Clone the repository.
2. Open the `index.html` file in a web browser.
3. Enter your date of birth in the input field.
4. Click the "Calculate Age" button.
5. Your age will be displayed in the result paragraph.

### Code Explanation

The code for this project is very simple. The HTML file contains a form with an input field and a button. The JavaScript file contains a function that calculates the user's age based on the date of birth they entered.

The following code snippet shows the HTML code for the age calculator:

### HTML

```
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Age Calculator</title>
    <link rel="stylesheet" href="style.css" />
  </head>
  <body>
    <div class="container">
      <h1>Age Calculator</h1>
      <div class="form">
        <label for="birthday">Enter you date of birth</label>
        <input type="date" id="birthday" name="birthday" />
        <button id="btn">Calculate Age</button>
        <p id="result">Your age is 21 years old</p>
      </div>
    </div>

    <script src="index.js"></script>
  </body>
</html>
```

The following code snippet shows the CSS code for the age calculator:

### CSS

```
body {
  margin: 0;
  padding: 20px;
  font-family: "Montserrat", sans-serif;
  background-color: #f7f7f7;
}

.container {
  background-color: white;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.2);
  padding: 20px;
  max-width: 600px;
  margin: 0 auto;
  border-radius: 5px;
  margin-top: 50px;
}

h1 {
  font-size: 36px;
  text-align: center;
  margin-top: 0;
  margin-bottom: 20px;
}

.form {
  display: flex;
  flex-direction: column;
  align-items: center;
}

label {
  font-weight: bold;
  margin-bottom: 10px;
}

input {
  padding: 8px;
  border: 1px solid #ccc;
  border-radius: 5px;
  width: 100%;
  max-width: 300px;
}

button {
  background-color: #007bff;
  color: white;
  border: none;
  padding: 10px 20px;
  border-radius: 5px;
  margin-top: 10px;
  cursor: pointer;
  transition: background-color 0.3s ease;
}

button:hover {
  background-color: #0062cc;
}

#result {
  margin-top: 20px;
  font-size: 24px;
  font-weight: bold;
}


```

The following code snippet shows the JavaScript code for the age calculator:

### javaScript

```
const btnEl = document.getElementById("btn");
const birthdayEl = document.getElementById("birthday");
const resultEl = document.getElementById("result");

function calculateAge() {
  const birthdayValue = birthdayEl.value;
  if (birthdayValue === "") {
    alert("Please enter your birthday");
  } else {
    const age = getAge(birthdayValue);
    resultEl.innerText = `Your age is ${age} ${age > 1 ? "years" : "year"} old`;
  }
}

function getAge(birthdayValue) {
  const currentDate = new Date();
  const birthdayDate = new Date(birthdayValue);
  let age = currentDate.getFullYear() - birthdayDate.getFullYear();
  const month = currentDate.getMonth() - birthdayDate.getMonth();

  if (
    month < 0 ||
    (month === 0 && currentDate.getDate() < birthdayDate.getDate())
  ) {
    age--;
  }

  return age;
}

btnEl.addEventListener("click", calculateAge);
```
