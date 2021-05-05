# Data Science Take Home 📊

Welcome to the data science take home! The data science take home that we provide here at Tesorio is used instead of many technical on-site (zoom or google hangouts) interviews over a long period.

## The Task

The task for the data science take home is to build a model that predicts when an **OPEN** invoice will be collected.

We provide you with two different datasets.

## The Datasets

The first data set is called `invoice.csv` and is very similar to the data set in the technical screening. The invoice dataset has information specific to an invoice. Here is a description of the columns:

1.	`id: int64` - The id of the invoice
2.	`due_date: object` - Date when the invoice is due
3.	`invoice_date: object` - The date when the invoice becomes active
4.	`status: object` - The status of the invoice. There are only two values `CLEARED` or `OPEN`. Note that it is possible for an invoice to be open but have a payment (partial payments)
5.	`amount: float` - The total amount of the invoice
6.	`currency: object` - The original currency of the invoice
7.	`company_id: int64` - The id of the company
8.	`customer_id: int64` - The id of the customer to which the invoice belongs
9. 	`account_id: int64` - The account in which the invoice has been attributed
10.	`cleared_date: object` - The date when the invoice was cleared
11.	`root_exchange_rate_value: float`: - Conversion value for the amount at the time the invoice was created. Assume the conversion is to `USD` for this exercise. For example, if the currency is `EUR` then this value will be the value needed to convert amount to `USD`.

The second data set is called `invoice_payments.csv`. This dataset give the information for the payment history of an invoice. It can be joined directly to the `invoice.csv` on the `invoice_id` columns.

1.	`amount: float` - This value is the amount that was paid towards the invoice. This value can be less than (partial payment) or equal to the original invoice amount
2.	`root_exchange_rate_value: float`	- Conversion amount at the time the transaction was made for the invoice.
3.	`transaction_date: object` - The date of the transaction
4. 	`invoice_id: int64` - The id of the invoice (can be used to join other invoice information)
5. 	`company_id: int64` - The id of the company that the invoice / transaction belongs to


## The Process

Everything needs to be written in Python. We are primarily a Python shop and all of our model implementations are written in Python 🐍. We are not evaluating how nice your code looks but please try and keep your code readable. You may write Python files or do your work in a jupyter notebook.

Every machine learning / deep learning project follows a process. What we are evaluating is the process of the ML lifecycle. Here is what we are looking for:

- **Exploratory Data Analysis** - A machine learning project is only as good as the data that goes into it. We do not expect the candidate to spend a large amount of time in this phase because of time restraints but what are some of the high level aspects of the data that you would want to know about? For example, what does the count of `CLEARED` vs. `OPEN` look like overall & for each company? Also, should we filter out any invoices? Are there any outliers?

- **Problem Formulation** - All of the projects we have so far are open questions from our customers. Problem formulation is one of the most important aspects of our job in data science. To reiterate the goal is to create a model that can predict when an **OPEN** invoice will be collected. 

- **Cross-Validation** - This is probably the most important step in determining the success of a machine learning / deep learning project. The ability to experiment and iterate depends directly on having a good cross-validation method set up. You need to set up a cross-validation / train-test split and document and discuss in detail why you chose a specific split & strategy.

- **Feature Engineering** - Good features also determine how far you can get with a machine learning / deep learning project (maybe not always true with deep learning?). We want you to construct any number of features that you can to create a more accurate and robust model. The more creative the better 🎨

- **Selecting a Metric & Model** - With the other features listed above in place you can now start the experimentation phase. What metric would you use to measure the success of your problem? You may also experiment with different models if you like but in the end we are looking for a single model with the "best" performance. How do you know this performs the "best"? If available (from the selected model) please also provide insights about which features you built drove the model decsion.

- **Predict** - Apply your selected model to the **OPEN** invoices in the `invoice.csv` 

- **Documentation** - please provide documentation / presentation on all of the bullet points listed above. This will be the end of any technical implementations but you should be able to defend your model and the audience be able to follow along with your notes / presentation. For the documentation please do not include any theoretical details about the models you choose and how they work. We are only looking for practical details from the steps listed above.

**BONUS**

We don't expect you to be able to do everything in this take home but if you want to add extra features becuase you are excited about the project we won't discourage it! Some of extra features could be:

1. Implementation of an automated hyper-parameter tuning package (optuna, hyper-opt)
2. Implementation of an experimental platform (neptune.ai)
3. Should we use a custom loss function? Implementing a custom loss. 
4. How would you serve your predictions to broader audience?

and any thing else you think would be fun to implement!	