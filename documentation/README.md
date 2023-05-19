README - LBG Learning-Oriented CRUD-based RESTful API
This repository contains an LBG learning-oriented CRUD-based RESTful API built using the Flask microframework. It is a conversion of the original NodeJS solution, closely following its structure and logic. Please note that this version combines LBYL (Look Before You Leap) and EAFP (Easier to Ask for Forgiveness than Permission) approaches to reflect simpler logic.

Installation and Setup
To run the API, follow these steps:

Ensure you have Python 3.x installed on your system.
Clone this repository to your local machine.
Install the required dependencies by running the following command:
pip install -r requirements.txt
Run the API using the following command:
python api.py --PORT <port_number>
Replace <port_number> with the desired port you want the API to listen on. By default, the API will listen on port 8080.
API Endpoints
The API provides the following endpoints:

Create an Item
URL: /create
Method: POST
Description: Creates a new item.
Request Body:
name (string): The name of the item.
description (string): The description of the item.
price (float): The price of the item.
Success Response:
Status Code: 201 (Created)
Response Body: JSON object representing the created item.
Error Response:
Status Code: 400 (Bad Request)
Response Body: Description of the encountered error.
Read All Items
URL: /read
Method: GET
Description: Retrieves all items.
Success Response:
Status Code: 200 (OK)
Response Body: JSON array containing all items.
Error Response:
Status Code: 400 (Bad Request)
Response Body: Description of the encountered error.
Read One Item
URL: /read/<item_id>
Method: GET
Description: Retrieves a single item by its ID.
URL Parameters:
item_id (integer): The ID of the item to retrieve.
Success Response:
Status Code: 200 (OK)
Response Body: JSON object representing the retrieved item.
Error Response:
Status Code: 400 (Bad Request)
Response Body: Description of the encountered error.
Update One Item
URL: /update/<item_id>
Method: PUT
Description: Updates a single item by its ID.
URL Parameters:
item_id (integer): The ID of the item to update.
Request Body:
name (string): The updated name of the item.
description (string): The updated description of the item.
price (float): The updated price of the item.
Success Response:
Status Code: 200 (OK)
Response Body: "OK" indicating a successful update.
Error Response:
Status Code: 400 (Bad Request)
Response Body: Description of the encountered error.
Delete One Item
URL: /delete/<item_id>
Method: DELETE
Description: Deletes a single item by its ID.
URL Parameters:
item_id (
integer): The ID of the item to delete.

Success Response:
Status Code: 200 (OK)
Response Body: "OK" indicating a successful deletion.
Error Response:
Status Code: 400 (Bad Request)
Response Body: Description of the encountered error.
Database Configuration
The API uses SQLite as its database. The database file is named data.db and will be created automatically when the API is run for the first time.

Logging
This version of the API uses simple print statements to output logs to the standard output (STDOUT) instead of a formalized logger. The logs include information about the executed operations, created, read, updated, and deleted items.

Miscellaneous
The API serves static files from the ./static directory.
The JavaScript/ES6 MIME Content type fix is applied to avoid any registry hacks.
Contributing
Feel free to contribute to this project by creating issues or submitting pull requests. Any improvements, bug fixes, or additional features are welcome.

License
This project is licensed under the MIT License. See the LICENSE file for more information.