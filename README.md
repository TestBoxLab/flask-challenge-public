We want to build a lead tracking app using:
- Flask as our framework
- Peewee as our database ORM

Our lead tracking app should

- Have a model called `Lead`, with the given fields
    - first name
    - last name
    - email
    - created at
- An API to which we can POST the lead information and store to the DB
- A scheduled job (You are free to decide how to schedule it) to run weekly posting the number of leads to an API endpoint:
    - Post to `https://api.retool.com/v1/workflows/6fda255b-a56a-4241-bd3d-10406f6f497a/startTrigger?workflowApiKey=retool_wk_3037c3d740f54d38b0fd7afe1eaa748e`
    - Send the number of leads created in the last week on the request body `{"number_of_leads":138}`

Analytics endpoint sample cURL
```bash
curl -X POST --url "https://api.retool.com/v1/workflows/6fda255b-a56a-4241-bd3d-10406f6f497a/startTrigger?workflowApiKey=retool_wk_3037c3d740f54d38b0fd7afe1eaa748e" --data '{"number_of_leads":138}' -H 'Content-Type: application/json'    
```