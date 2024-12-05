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
The architecture that will overwrite changes is Type 1 Slowly Changing Dimension (SCD). In this version of the CUSTOMER_ADDRESS table, each customer only has one address reocrd and whenever an adress changes, the old address is overwritten and the a column called LastUpdated (date) could be utilized to track when the address was modified. 

The architecture that would retain changes is called Type 2 SCD. In this version of the CUSTOMER_ADDRESS table, historical addresses are retained and any changes in customer addresses are added to the table as a new record with a start and end date. A boolean column called IsCurrent could be used to identify if it is the most recent active address.

There are privacy implications to retaining customer addresses, particularly with Type 2 SCD compared to Type 1 SCD. Storing a history of customer addresses using Type 2 architecture creates privacy issues if old addresses are kept indefinitely. For example, data breaches would be more serious with farther reaching implications. Therefore, it is probably in the best interest of the company to implement a corporate policy to regularly remove or expire customers' old addresses. 
```

## Question 4
Review the AdventureWorks Schema [here](https://imgur.com/a/u0m8fX6)

Highlight at least two differences between it and your ERD. Would you change anything in yours?
```
One difference is that the AdventureWorks Schema is much more detailed in specifying Primary Keys and Foreign Keys. Another thing that is different is that they don't appear to specify the type of relationships between keys (e.g., one-to-one, many-to-one), or the data type of each column. I would add the specification of Primary Keys and Foreign Keys into my schema but not remove the information about the relationships or data types.
```

# Criteria

[Assignment Rubric](./assignment_rubric.md)

# Submission Information

🚨 **Please review our [Assignment Submission Guide](https://github.com/UofT-DSI/onboarding/blob/main/onboarding_documents/submissions.md)** 🚨 for detailed instructions on how to format, branch, and submit your work. Following these guidelines is crucial for your submissions to be evaluated correctly.

### Submission Parameters:
* Submission Due Date: `September 28, 2024`
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

If you encounter any difficulties or have questions, please don't hesitate to reach out to our team via our Slack at `#cohort-4-help`. Our Technical Facilitators and Learning Support staff are here to help you navigate any challenges.
