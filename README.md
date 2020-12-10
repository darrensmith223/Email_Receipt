# Email_Receipt
Using SparkPost template language and substitution data to send an email receipt.  This is a working example of how to use nested loops within the SparkPost template language

The [SparkPost template language](https://developers.sparkpost.com/api/template-language/) is incredibly robust and able to support a range of logical operations, from simple variable substitution to if/else statements and array handling.  In this example, we will combine these elements together to create a template that can be used for Point of Sale (POS) receipts that can be sent to a consumer via email.

# The Premise
For this example, let’s imagine that we are implementing a POS system where the customer has the option of receiving their receipt via email.  The receipt we are creating will reflect a group order, where we will include the table number, each individual order, the contents of each order, and will include a message for each order made by a club member.
Let’s imagine that the group order contains two different orders, which have been described below:

Order 1 (Club Member):
* Sandwich; $10.00
* Chips; $2.50
* Soda; $1.99

Order 2:
* Pizza Slice; $2.00
* Soda; $1.99

# The Template
The template of our email receipt will be created as a SparkPost Stored Template, so that we can easily modify the HTML and access later.  The template is stored in this project as "Receipt-Template".

# The API Call
To send the message and pass the substitution data, the messages will need to be injected into SparkPost using the Transmissions API.  For this example, we will use Postman.  The information related to the submitted order is passed using substitution data.  The complete API call is included in this project as "Transmission-API-Call"


# How to Use This Example
* Store the template included in this project as a Stored Template within your SparkPost account using the template ID "email-receipt".
* Copy and Paste the API call included in this project in Postman - make sure to update the [hostname](https://developers.sparkpost.com/api/#header-endpoints) to correspond with the appropriate endpoint for your SparkPost account
* Update the body of the API call to include your email address as the recipient.
