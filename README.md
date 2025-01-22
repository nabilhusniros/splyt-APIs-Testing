# Splyt API Automation

## Collection Run Result

Below is a screenshot of the test run results for the Postman collection, showcasing the successful execution of all test cases:
![Run Collection](https://github.com/user-attachments/assets/bb92876f-63db-4dcc-9021-3aa02aec19d8)

## Prerequisites

1. Postman: Ensure you have Postman installed on your system. You can download it from Postman Official Website.
2. Git: Make sure Git is installed to clone this repository.

## Setup Instructions

1. Clone this repository to your local machine:

git clone ```https://github.com/nabilhusniros/splyt-APIs-Testing.git```
or you can download the zip files through github by following the steps mentioned in the screenshot
![1](https://github.com/user-attachments/assets/e0bf9e1d-1422-4457-ae26-4c93a4f60ea8)

2. Open Postman and import the collection and environment files:

* Import Collection:
    * Go to the Collections tab in Postman.
    * Click on Import.
    * Select the file Splyt API's.postman_collection from the cloned repository.

* Import Environment:
    * Go to the Environments tab in Postman.
    * Click on Import.
    * Select the file Splyt.postman_environment.json from the cloned repository.

3. Select the imported environment:

* Click on the Environment dropdown in the top-right corner of Postman.
* Select the Splyt environment.

## Running the Collection

1. Navigate to the Collections tab in Postman.
2. Click on the Splyt API collection.
3. Click on the Run button to open the Collection Runner.
4. Configure the following settings in the Collection Runner:
* Select the Splyt environment.
* Set the number of iterations if required.
5. Click Run Collection to execute the tests.

## Notes

* The environment variables are pre-configured for the current API endpoints and test data:
    * ```baseURL```: API base URL (https://qa-interview-test.qa.splytech.dev)
    * ```journeyId```: {{_id}} to extracting the ID from response

* Tests are included in the Postman collection for:
    * Positive and negative scenarios.
    * Response structure validation.
    * Status code validation.
    * Performance (response time within acceptable limits).
 
## Task

1. Find and identify as many bugs as possible on the endpoint created.
* Optional Fields:
    * No indication of how the API handles optional fields like passenger.surname
    * surname should be consider as Optional
    ```        
        "message": "\"surname\" is not allowed to be empty",
            "path": [
                "passenger",
                "surname"
            ],
            "type": "any.empty",
            "context": {
                "value": "",
                "invalids": [
                    ""
                ],
                "key": "surname",
                "label": "surname"
            }
        }
* No validation of Exceeding Maximum Value
    ```
    {
    "_id": "679106f96f6624adfd54fa82",
    "pickup": {
        "latitude": 500000000000000,
        "longitude": 200000000000
    },
    "departure_date": "2025-01-22T13:12:00.703Z",
    "passenger": {
        "name": "Nabillllllllllllllllllllllllllllllllllll",
        "surname": "Husni Rosllllllllllllllllllllllll",
        "phone_number": "+"
    }
}

2. What else should we be testing or checking for?
* Input validation
    * Ensure proper validation for all fields
* Test invalid Input
    * Missing fields.
    * Empty strings.
    * Incorrect data types (e.g., string instead of number for latitude).
    * Boundary values for numerical fields.
* GET /api/journeys/:journey_id:
    * Test with valid and invalid journey_id.
    * Check response format, status codes, and error handling for invalid or non-existent ID.

3. What can be done to ensure testing quality and quality of the service?
* Automated Testing:
    * Implement test suites using tools like Postman/Newman or Cypress to validate all API functionality and edge cases automatically.
* Comprehensive Documentation:
    * Provide clear API documentation detailing required/optional fields, expected responses, and error codes.

4. What problems/challenges you faced in testing and working on this tech task
* Limited documentation made assumptions necessary about the API’s behavior, such as expected error codes or edge-case handling.

5. Provide test cases and automated testing implementations (Optional)
* Provided in the script of each test cases

6. How can this tech task be improved? (Optional)
* Clearer Documentation:
    * Include detailed specifications for expected responses, error codes, and examples for both valid and invalid cases.


