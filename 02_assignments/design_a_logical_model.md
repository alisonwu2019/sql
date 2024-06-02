# Assignment 1: Design a Logical Model

## Question 1
Create a logical model for a small bookstore. 📚

At the minimum it should have employee, order, sales, customer, and book entities (tables). Determine sensible column and table design based on what you know about these concepts. Keep it simple, but work out sensible relationships to keep tables reasonably sized. Include a date table. There are several tools online you can use, I'd recommend [_Draw.io_](https://www.drawio.com/) or [_LucidChart_](https://www.lucidchart.com/pages/).
[assignment-1_q1.pdf](assignment-1_q1.pdf)

## Question 2
We want to create employee shifts, splitting up the day into morning and evening. Add this to the ERD.
[assignment-1_q2.pdf](assignment-1_q2.pdf)

## Question 3
The store wants to keep customer addresses. Propose two architectures for the CUSTOMER_ADDRESS table, one that will retain changes, and another that will overwrite. Which is type 1, which is type 2?

_Hint, search type 1 vs type 2 slowly changing dimensions._

[assignment-1_q3.pdf](assignment-1_q3.pdf)
```
1. customer_address table - type 1 sdc: Any updates to a customer's address will directly overwrite the existing information in the CUSTOMER_ADDRESS table. This means that only the latest address details will be retained, and historical changes will be lost.
2. customer_address table - type 2 sdc: When a new address is added for a customer, set the most_recent_flag to true for the new address and false for any previous addresses for the same customer.
```

Bonus: Are there privacy implications to this, why or why not?
```
Yes for both type 1 and type 2 sdc. 
type 1 sdc: Privacy implications primarily revolve around the risk of data accuracy and potential exposure of outdated information. If an incorrect address is overwritten with a new one, it may lead to inaccuracies in customer records.
type 2 sdc: Privacy implications extend to both the accuracy and retention of historical data. While this design preserves the history of customer addresses, it also means that outdated information remains accessible in the database. 
```

## Question 4
Review the AdventureWorks Schema [here](https://i.stack.imgur.com/LMu4W.gif)

Highlight at least two differences between it and your ERD. Would you change anything in yours?
```
The AdventureWorks schema and the ERD I provided exhibit differences in their structures. AdventureWorks employs a hierarchical approach to product categorization through the ProductCategory table, allowing for organization into a parent-child hierarchy, whereas my ERD lacks such hierarchical categorization for books. 
Also, there are tables such as Employee and EmployeeDepartmentHistory, which likely contain information about employees, their departments, and historical changes. In contrast, the ERD I provided focuses solely on entities relevant to a bookstore scenario, such as books, customers, sales, and orders. 
To make the ERD more comprehensive, it may be beneficial to include tables related to employees and human resources if managing employee information and organizational structure is essential for the bookstore's operations.
```

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
