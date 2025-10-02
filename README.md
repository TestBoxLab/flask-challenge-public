# Lead Tracking App - Technical Challenge

Welcome to the Lead Tracking App technical challenge! This repository contains the requirements for a coding exercise designed to assess your backend engineering and solution design skills. Please read the instructions carefully and structure your solution as you see fit.

## Challenge Overview

Your task is to build a simple lead tracking REST application using the following technologies:

- **Flask** as the web framework
- **Peewee** as the ORM for database interactions

The application should allow submitting and retrieving `Lead` information, store it in a database, and provide basic analytics via a scheduled job.

---

## Requirements

### 1. Lead Model

Implement a `Lead` model with the following fields:

- `first_name`
- `last_name`
- `email`
- `created_at`

### 2. API Endpoints

Provide two RESTful API endpoints:
- Add a new lead (POST)
- List all leads with optional creation date filtering (GET)

### 3. Scheduled Analytics Job

Implement a scheduled job that runs **once per week**. You are free to decide how to design this solution, but the job should:

- Count the number of leads created in the previous one week period.
- POST this number to the following external API endpoint:

  ```
  https://api.retool.com/v1/workflows/6fda255b-a56a-4241-bd3d-10406f6f497a/startTrigger?workflowApiKey=retool_wk_3037c3d740f54d38b0fd7afe1eaa748e
  ```

- The request body should be JSON in the following format (example):

  ```json
  {
    "number_of_leads": 138
  }
  ```

#### Example cURL Request

```
curl -X POST --url "https://api.retool.com/v1/workflows/6fda255b-a56a-4241-bd3d-10406f6f497a/startTrigger?workflowApiKey=retool_wk_3037c3d740f54d38b0fd7afe1eaa748e" --data '{"number_of_leads":138}' -H 'Content-Type: application/json'    
```
## Evaluation Criteria

During this challenge, your skills will be evaluated based on the following criteria:

- **Technical Execution and Code Quality:**  
  - How well your code is written, including readability, maintainability, adherence to best practices, and correct implementation of requirements.

- **Solution Design and Problem-Solving:**  
  - How you break down and solve problems, and the effectiveness and scalability of your solutions.

- **Collaboration and Communication:**  
  - How you communicate your ideas and thought process, explain your work and decisions, and collaborate throughout the development process.