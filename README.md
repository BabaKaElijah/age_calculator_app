# 📆 Age Calculator App

The Age Calculator is a simple web app that calculates a person's age in **years, months, and days** based on their date of birth. It's built with **HTML, CSS, and JavaScript** and is perfect for beginner practice or use in small projects.

---

## 🧮 Features

- Select your birthdate using a date picker
- Calculates your exact age (e.g. `24 years 3 months 12 days old`)
- Prevents selecting future dates
- Clean and responsive user interface
- Styled output below the input

---

## 🚀 Demo

![Age Calculator Screenshot](screenshot.PNG)

---

## 📂 Project Structure
```
age-calculator/
│
├── index.html # Main HTML file
├── style.css # Custom styling
├── age-calculator.png # Screenshot
```

---

## 🛠️ Technologies Used

- HTML5
- CSS3
- JavaScript 

---
## 📆 Age Calculator Logic (JavaScript)

This function calculates the age based on a user's inputted birth date and today's date. It accounts for day and month differences to provide an accurate age breakdown.

```javascript
let userInput = document.getElementById('date');
userInput.max = new Date().toISOString().split('T')[0];

function calculateAge() {
  let birthDate = new Date(userInput.value);
  let today = new Date();

  let birthDay = birthDate.getDate();
  let birthMonth = birthDate.getMonth() + 1;
  let birthYear = birthDate.getFullYear();

  let currentDay = today.getDate();
  let currentMonth = today.getMonth() + 1;
  let currentYear = today.getFullYear();

  let year = currentYear - birthYear;
  let month = currentMonth - birthMonth;
  let day = currentDay - birthDay;

  // Adjust if day is negative
  if (day < 0) {
    month--;
    let prevMonth = new Date(currentYear, currentMonth - 1, 0).getDate();
    day += prevMonth;
  }

  // Adjust if month is negative
  if (month < 0) {
    year--;
    month += 12;
  }

  const result = `You are ${year} year${year !== 1 ? 's' : ''} ${month} month${month !== 1 ? 's' : ''} ${day} day${day !== 1 ? 's' : ''} old`;
  document.getElementById('result').textContent = result;
}
```

## ✅ How to Use

1. Clone the repository:

```bash
git clone https://github.com/your-username/age-calculator.git
```
2. Open the folder in your code editor

3. Open index.html in your browser

4. Select a date of birth and click "Calculate"


## 🙌 Author
Developed by Ellias Sithole
