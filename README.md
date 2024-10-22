# Application 1: Rule Engine using AST


## Overview
This application functions as a rule engine that assesses user eligibility based on various attributes, including age, department, salary, and experience. It employs an Abstract Syntax Tree (AST) for representing and managing conditional rules, facilitating the dynamic creation, combination, and evaluation of rules.

## Features
- *Rule Creation*: Users can define rules using a string format, which is then transformed into an AST.
  
![Screenshot 2024-10-22 144202](https://github.com/user-attachments/assets/8f4f6081-c023-4f70-84f7-14bfe35b794f)

- *Rule Combination*: Allows the merging of multiple rules into a singular AST to enable more intricate evaluations.

![Screenshot 2024-10-22 144409](https://github.com/user-attachments/assets/b95d99ea-4f44-4d26-86ac-6f3c8d52c112)

- *Rule Evaluation*: Assesses whether the provided data aligns with the criteria set by the AST.

![Screenshot 2024-10-22 144343](https://github.com/user-attachments/assets/54164383-3cbe-47a0-8e48-38be47d7b375)

- *Tree Visualization*: When defining or combining rules, a tree representation will be displayed for better understanding.

## Tech Stack
- *Backend*: Node.js, Express.js
- *Database*: MongoDB

## Getting Started

### Prerequisites
Ensure you have Node.js and npm installed on your machine.

### Installation Steps
1. Clone the Repository:
   bash
   git clone "(https://github.com/avanti77/Rule-Engine-with-AST-main).git"
   

2. Navigate to the project directory:
   bash
   cd Application-1-Rule-Engine-with-AST
   

3. Install the Backend Dependencies:
   bash
   npm install
   

4. Create a .env file in the root directory and add your MongoDB URL:
   env
   MONGO_URL=""
   

5. Launch the Server:
   bash
   npm start
   

## API Endpoints

### Create a Rule
- *Endpoint*: /api/create_rule
- *Method*: POST
- *Request Body*:
  json
  {
    "ruleString": "((age > 30 AND department = 'Sales') OR (age < 25 AND department = 'Marketing')) AND (salary > 50000 OR experience > 5)",
    "ruleName": "Rule-1"
  }
  
  *Note*: Ensure that there are appropriate spaces in the rule for accurate results. The rule should follow this format: variable operator value.

- *Response*: 
  json
  {
    "message": "Rule created successfully",
    "ruleId": "abc123"
  }
  
![s3](https://github.com/user-attachments/assets/fabe26c4-170f-4890-b8ea-9b51774b3cf0)

### Combine Rules
- *Endpoint*: /api/rules/combine_rules
- *Method*: POST
- *Request Body*:
  json
  {
    "rules": [
      { "ruleId": "ruleId1" },
      { "ruleId": "ruleId2" }
    ]
  }
  

- *Response*:
  json
  {
    "message": "Rules combined successfully",
    "combinedRuleId": "xyz789"
  }
  

### Evaluate a Rule
- *Endpoint*: /api/rules/evaluate_rule
- *Method*: POST
- *Request Body*:
  json
  {
    "rule": { "ruleId": "abc123" },
    "data": {
      "age": 35,
      "department": "Sales",
      "salary": 60000,
      "experience": 3
    }
  }
  

- *Response*:
  json
  {
    "result": true
  }
  

## Running Tests
You can implement and execute tests to verify that everything is functioning as expected.

