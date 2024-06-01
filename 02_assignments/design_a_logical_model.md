# Assignment 1: Design a Logical Model

## Question 1
Create a logical model for a small bookstore. 📚

At the minimum it should have employee, order, sales, customer, and book entities (tables). Determine sensible column and table design based on what you know about these concepts. Keep it simple, but work out sensible relationships to keep tables reasonably sized. Include a date table. There are several tools online you can use, I'd recommend [_Draw.io_](https://www.drawio.com/) or [_LucidChart_](https://www.lucidchart.com/pages/).

## Question 2
We want to create employee shifts, splitting up the day into morning and evening. Add this to the ERD.

## Question 3
The store wants to keep customer addresses. Propose two architectures for the CUSTOMER_ADDRESS table, one that will retain changes, and another that will overwrite. Which is type 1, which is type 2?

_Hint, search type 1 vs type 2 slowly changing dimensions._

Bonus: Are there privacy implications to this, why or why not?
```
Your answer...
Type 1: 
CUSTOMER_ADDRESS Table:

Columns:
customer_id 
address
city
state
postal_code
In this design, when a customer's address changes, the existing record in the CUSTOMER_ADDRESS table would be updated with the new address details. There's no need for additional columns to track historical changes.

Type 2: Retain Changes:
CUSTOMER_ADDRESS Table:

Columns:
customer_address_id 
customer_id 
address
city
state
postal_code
start_date
end_date (nullable)
In this design, when a customer's address changes, a new record is inserted into the CUSTOMER_ADDRESS table with the updated address details along with the start date of validity. The end date field can be used to mark the end of validity for the previous address, which remains open-ended until the next change occurs. This allows for a historical view of the customer's addresses over time.

So, the Type 1 architecture overwrites existing data with each change, while the Type 2 architecture retains historical changes by adding new records with start and end dates to track the history of customer addresses.

Yes, there are privacy implications to this. There is still a risk if unauthorized individuals gain access to the system and view the current address information
```

## Question 4
Review the AdventureWorks Schema [here](https://i.stack.imgur.com/LMu4W.gif)

Highlight at least two differences between it and your ERD. Would you change anything in yours?
```
Your answer...
This ERD is more detailed compared to mine. It is divided into different sections like sales, purchases, person, HR, etc. In this ERD, primary and foreign keys are identified.
I would definitely add sections; it's really handy, and more tables related to orders and sales.

# Criteria

[Assignment Rubric](./assignment_rubric.md)

# Submission Information

🚨 **Please review our [Assignment Submission Guide](https://github.com/UofT-DSI/onboarding/blob/main/onboarding_documents/submissions.md)** 🚨 for detailed instructions on how to format, branch, and submit your work. Following these guidelines is crucial for your submissions to be evaluated correctly.

### Submission Parameters:
* Submission Due Date: `June 1, 2024`
* The branch name for your repo should be: `model-design`
* What to submit for this assignment:
    * This markdown (design_a_logical_model.md) should be populated.
    * Two Entity-Relationship Diagrams (preferably in a pdf, jpeg, png format).
* What the pull request link should look like for this assignment: `https://github.com/<your_github_username>/sql/pull/<pr_id>`
    * Open a private window in your browser. Copy and paste the link to your pull request into the address bar. Make sure you can see your pull request properly. This helps the technical facilitator and learning support staff review your submission easily.

Checklist:
- [ ] Create a branch called `model-design`.
- [ ] Ensure that the repository is public.
- [ ] Review [the PR description guidelines](https://github.com/UofT-DSI/onboarding/blob/main/onboarding_documents/submissions.md#guidelines-for-pull-request-descriptions) and adhere to them.
- [ ] Verify that the link is accessible in a private browser window.

If you encounter any difficulties or have questions, please don't hesitate to reach out to our team via our Slack at `#cohort-3-help`. Our Technical Facilitators and Learning Support staff are here to help you navigate any challenges.
