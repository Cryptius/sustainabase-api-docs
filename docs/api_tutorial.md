# Getting Started

The API route is composed of a base URL plus a route path.

The base URL is:

`https://o0cj2w35kc.execute-api.us-east-1.amazonaws.com/prod/activities`

Each activity record category is associated with a route path, defined in the API Reference. These route paths 

Each route accepts a list of JSON objects formatted like:

    [
        {
            [field name]: [value]
        },
        [...]
    ]

The list can contain up to 50 activity records for storage.

For example, a submission of two activity records to scope1/stationary-combustion could look like:

    [
        {
            "building_address": "123 Sesame Street",
            "provider_name": "Big Bird",
            "account_number": 1234,
            "date": "4/1/2022",
            "fuel_type": "propane",
            "total_amount": 650.00,
            "unit": "gallons",
            "total_cost": 567.89
        },
        {
            "building_address": "123 Sesame Street",
            "provider_name": "Big Bird",
            "account_number": 1234,
            "date": "3/1/2022",
            "fuel_type": "propane",
            "total_amount": 900.00,
            "unit": "gallons",
            "total_cost": 1050.50
        }
    ]

Every required field must be present for data to be landed. Allowed fields may or may not be present. Expected types are strings, integers or floating point decimals. All dates are strings formatted as "MM-DD-YYYY". Required and allowed fields are drawn from "Sustainabase Data Requests_ROMANO-METHOD.xlsx".

API requests are given an 'Authorization' header with an ID token, to be obtained from the Cognito hosted authentication UI or directly from the Sustainabase team.

Several responses are possible.

#### 200 OK

Everything went well. The body of the response contains information about how many activities were stored and where.

#### 500 Internal Server Error

This means the API resource or data are incomplete in some way, and the activity has not been stored.

This can happen in case of the following problems with the request:

* Route is not recognized
* Missing required field for category
* Included field not available in category
* Too many records included in request

# Tutorials

### Use Case: Submitting Scope 1 - Stationary Combustion activity data

1. Retrieve ID token with Cognito login information.
2. Sample JSON payload:

        [
            {
                "provider_name": "AAA Gas Inc.",
                "account_number": "12345",
                "date": "01-01-2021",
                "fuel_type": "propane",
                "total_amount": 500.00,
                "unit": "gallons",
                "building_address": "Union St, Anywhere, FL",
                "total_cost": 500.00
            }
        ]

3. POST request to:

`https://o0cj2w35kc.execute-api.us-east-1.amazonaws.com/prod/activities/scope1/stationary-combustion`

4. Successful response:

`1 objects placed in scope1/stationary-combustion`

### Use Case: Submitting Scope 2 - Owned Utilities data

1. Retrieve ID token with Cognito login information
2. Sample JSON payload:

        [
            {
                "facility_address":"Union St, Anywhere, FL",
                "provider_name":"Electric Company Inc",
                "account_number":"11111555555555",
                "begin_date":"2021-01-01",
                "end_date":"2021-01-31",
                "total_amount":50000,
                "unit":"kWh",
                "activity_type":"Electricity"
            }
        ]

3. POST request to:

`https://o0cj2w35kc.execute-api.us-east-1.amazonaws.com/prod/activities/scope2/utilities/owned`

4. Successful response:

`1 objects placed in scope2/utlities/owned`

### Use Case: Submitting Scope 3 - Purchased Packaging - Average data

1. Retrieve ID token with Cognito login information
2. Sample JSON payload:

        [
            {
                "supplier":"ABC Plastics",
                "packaging_type":"5 oz bottles",
                "packaging_material":"HDPE",
                "pct_recycled_content":"0,
                "other_sustainable_certifications":"None",
                "date":"2021-01-31",
                "total_weight":300.00,
                "unit":"lbs"
            }
        ]

3. POST request to:

`https://o0cj2w35kc.execute-api.us-east-1.amazonaws.com/prod/activities/scope3/purchased-packaging/average-data`

4. Successful response:

`1 objects placed in scope3-purchased-packaging/average-data`