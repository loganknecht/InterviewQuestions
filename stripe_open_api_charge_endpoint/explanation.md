# API Specification Document

Today we're going to be looking at `Stripes` Open API Specification

https://github.com/stripe/openapi/tree/master/openapi

Specifically we're going to be looking at the `charges` endpoint and how its `POST` operation works

We want to make sure that it's reasonably tested and have the means assure our team that we know it's valid and durable.

## Assumptions

-   Previous request have been made to configure `Accounts`
    -   A `Card` has already been created
-   Existing data is valid
-   Don't need to test the existing data for what will be used in `properties`
-   White box environment
    -   Means you have access to the entire pipeline and code

## Task Request

Using this endpoint, explain to me how you would approach testing it

-   Request?
-   Response?
-   Behind the scenes data?

### Grading

-   Not graded on completeness
-   Not graded on thoroughness
-   This is a discussion to understand how you would approach testing when placed into an environment where you are unfamiliar with the code
-   Minimum Testing Coverage
    -   Required information MUST be tested
        -   `paths."/v1/charges".post.requestBody.content.application/x-www-form-urlencoded.schema`
            -   `properties.card.exp_month`
            -   `properties.card.exp_year`
            -   `properties.card.number`
            -   `properties.destination.account`
            -   `properties.shipping.address.line1`
            -   `properties.shipping.name`
            -   `properties.transfer_data.destination`
-   Optional Testing Coverage
    -   Everything else

### Want to See

-   Method stubs/class definitions highlighting test cases
-   Want to see explicit list of areas being tested
-   Thought process
-   Best efforts to guard against areas of friction
    -   Security
    -   Scalability
    -   Future proofing
    -   Gotchas
