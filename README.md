# Ex06 BMI Calculator
## Date:
### Name : Archana K
### Reg no: 212222240011

## AIM
To create a BMI calculator using React Router 

## ALGORITHM
### STEP 1 State Initialization
Manage the current page (Home or Calculator) using React Router.

### STEP 2 User Input
Accept weight and height inputs from the user.

### STEP 3 BMI Calculation
Calculate the BMI based on user input.

### STEP 4 Categorization
Classify the BMI result into categories (Underweight, Normal weight, Overweight, Obesity).

### STEP 5 Navigation
Navigate between pages using React Router.

## PROGRAM
### BHI.jsx
```
import React, { useState } from 'react';
import './App.css';

function App() {
  const [weight, setWeight] = useState('');
  const [height, setHeight] = useState('');
  const [bmi, setBmi] = useState(null);
  const [message, setMessage] = useState('');

  const calculateBMI = (e) => {
    e.preventDefault();

    if (!weight || !height) {
      alert('Please enter both weight and height.');
      return;
    }

    const heightInMeters = height / 100;
    const bmiValue = (weight / (heightInMeters * heightInMeters)).toFixed(2);

    setBmi(bmiValue);

    if (bmiValue < 18.5) setMessage('Underweight');
    else if (bmiValue >= 18.5 && bmiValue < 24.9) setMessage('Normal weight');
    else if (bmiValue >= 25 && bmiValue < 29.9) setMessage('Overweight');
    else setMessage('Obese');
  };

  return (
    <div className="bmi-container">
      <h1>BMI Calculator</h1>
      <form onSubmit={calculateBMI}>
        <input
          type="number"
          placeholder="Weight (kg)"
          value={weight}
          onChange={(e) => setWeight(e.target.value)}
        />
        <input
          type="number"
          placeholder="Height (cm)"
          value={height}
          onChange={(e) => setHeight(e.target.value)}
        />
        <button type="submit">Calculate</button>
      </form>

      {bmi && (
        <div className="result">
          <h2>Your BMI: {bmi}</h2>
          <p>Status: {message}</p>
        </div>
      )}
    </div>
  );
}

export default App;
```
## App.css
```
.bmi-container {
  text-align: center;
  margin-top: 50px;
  font-family: Arial, sans-serif;
}

form {
  margin: 20px;
}

input {
  margin: 10px;
  padding: 8px;
  width: 200px;
  font-size: 16px;
}

button {
  padding: 10px 20px;
  font-size: 16px;
  cursor: pointer;
}

.result {
  margin-top: 20px;
  font-size: 20px;
}
```
## output
![image](https://github.com/user-attachments/assets/77831423-50e7-4387-b7b8-77881f529653)

## Result
The program for creating BMI Calculator using React Router is executed successfully.
