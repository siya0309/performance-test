# BODMAS Quiz Test

## Project Overview

The BODMAS Quiz Test is an interactive web-based learning application designed to help students understand and practice the BODMAS rule (Brackets, Orders, Division, Multiplication, Addition, Subtraction).

The application evaluates a student's performance before and after learning the concept through a simple quiz-based approach. It records scores and completion times and stores the results in Google Sheets using Google Apps Script.

---

## Objectives

* Assess the student's initial understanding of BODMAS.
* Provide guided practice with step-by-step examples.
* Measure learning improvement through a post-practice quiz.
* Record user performance data for analysis.
* Statistically evaluate learning effectiveness using a paired t-test.

---

## Technologies Used

* HTML5
* CSS3
* JavaScript
* Google Apps Script
* Google Sheets
* Google Fonts

---

## Features

### 1. User Registration

Students enter their name before starting the quiz.

### 2. Pre-Test Assessment

A multiple-choice question evaluates the student's initial BODMAS knowledge.

Information collected:

* Score
* Time Taken

### 3. Interactive Learning Section

Students learn the BODMAS concept through:

* Step-by-step examples
* Practice calculations
* Visual explanations

### 4. Countdown Timer

A 10-minute timer is provided during the learning phase.

### 5. Post-Test Assessment

A second multiple-choice question measures improvement after practice.

Information collected:

* Score
* Time Taken

### 6. Automatic Data Storage

Results are sent to Google Sheets using Google Apps Script.

Stored Data:

* Student Name
* Before-Test Score
* Before-Test Time
* After-Test Score
* After-Test Time

### 7. Attractive User Interface

Includes:

* Purple gradient background
* Floating mathematical expressions animation
* Orbitron and Poppins fonts
* Responsive card layout

---

## Application Workflow

```text
Enter Name
      ↓
Start Pre-Test
      ↓
Submit Answer
      ↓
Display Score & Time
      ↓
Open Practice Section
      ↓
10 Minute Learning Session
      ↓
Post-Test Appears
      ↓
Submit Final Answer
      ↓
Display Results
      ↓
Save Data to Google Sheets
```

---

## BODMAS Rule

BODMAS stands for:

| Letter | Meaning        |
| ------ | -------------- |
| B      | Brackets       |
| O      | Orders         |
| D      | Division       |
| M      | Multiplication |
| A      | Addition       |
| S      | Subtraction    |

### Example

Expression:

```
12 + 6 × 3
```

Step 1:

```
6 × 3 = 18
```

Step 2:

```
12 + 18 = 30
```

Final Answer:

```
30
```

---

## Google Sheets Integration

The application uses the Fetch API to send JSON data to a Google Apps Script Web App.

Example Data Sent:

```json
{
  "name": "John",
  "beforeTime": "12.5",
  "afterTime": "8.2",
  "beforeScore": 0,
  "afterScore": 1
}
```

Example JavaScript:

```javascript
fetch(url,{
   method:"POST",
   body:JSON.stringify(data)
})
```

---

## Statistical Analysis Using Paired t-Test

### Purpose

To determine whether the BODMAS learning module significantly improved student performance, a paired t-test was conducted using the scores collected before and after practice.

### Why a Paired t-Test?

A paired t-test is appropriate because the same students take both the pre-test and post-test. Since the observations come from the same individuals, the scores are dependent (paired).

### Hypotheses

**Null Hypothesis (H₀):**

There is no significant difference between the mean pre-test and post-test scores.

[
H_0 : \mu_d = 0
]

**Alternative Hypothesis (H₁):**

There is a significant difference between the mean pre-test and post-test scores.

[
H_1 : \mu_d \neq 0
]

where ( \mu_d ) represents the mean difference between post-test and pre-test scores.

### Procedure

1. Collect pre-test scores from participants.
2. Collect post-test scores from the same participants.
3. Calculate the score difference for each participant.
4. Compute the mean and standard deviation of the differences.
5. Perform a paired t-test.
6. Compare the p-value with the significance level (α = 0.05).

### Interpretation

* If **p-value < 0.05**, reject the null hypothesis and conclude that the learning module significantly improved student performance.
* If **p-value ≥ 0.05**, fail to reject the null hypothesis and conclude that there is insufficient evidence of improvement.

### Significance to the Project

The paired t-test provides statistical evidence regarding the effectiveness of the BODMAS learning module. Instead of relying only on score comparisons, the test scientifically validates whether the observed improvement is statistically significant.

---

## Learning Outcomes

After completing the quiz, students should be able to:

* Apply the BODMAS rule correctly.
* Solve arithmetic expressions in the proper order.
* Improve their speed and accuracy in calculations.
* Demonstrate learning progress through pre-test and post-test assessments.

---

## Future Enhancements

* Multiple quiz questions
* Random question generation
* Difficulty levels (Easy, Medium, Hard)
* Progress charts and analytics dashboard
* User login system
* Leaderboard
* Certificate generation
* Mobile-responsive optimization

---

## Conclusion

The BODMAS Quiz Test is an educational web application that combines assessment, learning, data collection, and statistical analysis in a single platform. By comparing student performance before and after practice and validating the results using a paired t-test, the project provides a data-driven approach to measuring learning effectiveness and understanding of the BODMAS rule.
