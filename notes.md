# Habit Tracker Project

A habit tracker is an application designed to help users build and maintain good habits by tracking their daily activities. Here’s a detailed explanation of the features, technologies, and structure of the project:

## Features

1. **User Authentication**:
   - **Sign Up/Login**: Users can create an account and log in.
   - **Profile Management**: Users can update their profile information.

2. **Habit Creation**:
   - **Add New Habit**: Users can create new habits they want to track (e.g., exercise, reading, meditation).
   - **Set Frequency**: Users can set the frequency of the habit (daily, weekly, etc.).

3. **Daily Tracking**:
   - **Mark as Done**: Users can mark their habits as done for the day.
   - **View Calendar**: Users can view a calendar showing which days they completed their habits.

4. **Streaks and Progress**:
   - **Streak Counter**: Display the number of consecutive days a habit has been completed.
   - **Progress Charts**: Visualize progress over time using charts and graphs.

5. **Reminders**:
   - **Notifications**: Send reminders to users to complete their habits.

6. **Dashboard**:
   - **Overview**: A dashboard showing an overview of all habits, progress, and streaks.

## Technologies

- **Frontend**: React.js
  - Components: To create reusable UI elements.
  - State Management: Use state and props to manage data flow within the app.
  
- **Backend**: Node.js and Express.js
  - RESTful API: Create endpoints for user authentication, habit creation, and progress tracking.

- **Database**: MongoDB
  - Collections: Users, Habits, Progress.
  - Schema Design: Define schemas for users, habits, and progress records.

- **Additional Libraries/Tools**:
  - **Mongoose**: For MongoDB object modeling.
  - **JWT (JSON Web Tokens)**: For secure authentication.
  - **Nodemailer**: For sending reminder emails.
  - **React-Calendar**: For displaying calendar views.
  - **Chart.js**: For creating progress charts.

#### Project Structure

1. **Frontend**:
   - **Components**: 
     - `Header.js`: Navigation bar.
     - `HabitForm.js`: Form to create new habits.
     - `HabitList.js`: List of all habits.
     - `HabitDetail.js`: Detail view of a specific habit.
     - `Calendar.js`: Calendar view for tracking.
     - `Dashboard.js`: Overview of all habits and progress.
   - **Pages**:
     - `SignUp.js`: User registration.
     - `Login.js`: User login.
     - `Profile.js`: User profile management.
     - `Home.js`: Main page after login showing the dashboard.

2. **Backend**:
   - **Routes**:
     - `auth.js`: Authentication routes (sign up, login).
     - `habits.js`: Routes for creating, updating, and deleting habits.
     - `progress.js`: Routes for tracking progress.
   - **Models**:
     - `User.js`: Schema for user information.
     - `Habit.js`: Schema for habit details.
     - `Progress.js`: Schema for tracking progress.
   - **Controllers**:
     - `authController.js`: Handle authentication logic.
     - `habitController.js`: Handle habit-related logic.
     - `progressController.js`: Handle progress tracking logic.
<!--
#### Example Code Snippets

**Frontend (React Component for Habit Creation)**:
```jsx
import React, { useState } from 'react';

const HabitForm = ({ addHabit }) => {
  const [name, setName] = useState('');
  const [frequency, setFrequency] = useState('daily');

  const handleSubmit = (e) => {
    e.preventDefault();
    addHabit({ name, frequency });
    setName('');
  };

  return (
    <form onSubmit={handleSubmit}>
      <input
        type="text"
        value={name}
        onChange={(e) => setName(e.target.value)}
        placeholder="Habit Name"
        required
      />
      <select value={frequency} onChange={(e) => setFrequency(e.target.value)}>
        <option value="daily">Daily</option>
        <option value="weekly">Weekly</option>
      </select>
      <button type="submit">Add Habit</button>
    </form>
  );
};

export default HabitForm;
```

**Backend (Express Route for Adding a Habit)**:
```javascript
const express = require('express');
const router = express.Router();
const Habit = require('../models/Habit');

// Add a new habit
router.post('/habits', async (req, res) => {
  const { name, frequency, userId } = req.body;

  try {
    const newHabit = new Habit({ name, frequency, user: userId });
    await newHabit.save();
    res.status(201).json(newHabit);
  } catch (error) {
    res.status(400).json({ message: error.message });
  }
});

module.exports = router;
```
-->
This project provides a practical way to teach intermediate students about the MERN stack, incorporating both basic and slightly advanced concepts in web development.
