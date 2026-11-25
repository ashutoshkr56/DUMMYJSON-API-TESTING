# E-Commerce CRUD API Automation Using Postman

## 1. Project Overview

This project focuses on API testing and automation of an E-Commerce System using **Postman** and the **DummyJSON Public API**.

It tests different API operations such as Create, Read, Update, and Delete (CRUD) for products and shopping carts. It also covers user authentication, token management, product searching, and negative testing.

Postman test scripts are used to automatically validate HTTP status codes, response data, response time, and other API conditions.

## 2. Technologies Used

- **Postman:** API testing and automation.
- **DummyJSON API:** Public REST API for testing.
- **JavaScript:** Writing automated test scripts.
- **JSON:** Sending request data and validating API responses.
- **REST API:** Communication using HTTP methods.

## 3. API Base URL

```text
https://dummyjson.com
```

## 4. Project Features

### Authentication
- User login with valid credentials.
- Get current authenticated user.
- Refresh access and refresh tokens.
- Store authentication tokens using Postman environment variables.

### Products Management
- Create a new product.
- Retrieve all products.
- Retrieve a single product.
- Update product details.
- Search products.
- Retrieve product categories.

### Shopping Cart Management
- Create a shopping cart.
- Retrieve all shopping carts.
- Retrieve carts by user ID.
- Update cart products and quantities.
- Delete a shopping cart.

### User Management
- Retrieve all users.
- Retrieve a single user.
- Search users.
- Get current user.
- Add a new user.
- Update user information.

### Negative Testing
- Login with an incorrect password.
- Delete a non-existing shopping cart.

## 5. HTTP Methods Used

| Method | Purpose |
|---|---|
| GET | Retrieve data |
| POST | Create new data |
| PUT | Update existing data |
| DELETE | Delete data |

## 6. Environment Variables

The following Postman environment variables are used:

| Variable | Purpose |
|---|---|
| `base_url` | Base URL of DummyJSON API |
| `access_token` | Stores authentication access token |
| `refresh_token` | Stores refresh token |
| `user_id` | Stores authenticated user ID |
| `product_id` | Stores newly created product ID |
| `cart_id` | Stores newly created cart ID |

Set the `base_url` variable to:

```text
https://dummyjson.com
```

Other variables are automatically updated by the test scripts when the relevant requests are executed.

## 7. Test Automation

Postman JavaScript test scripts are used to automate API validation.

Some important validations include:

- Checking HTTP status codes.
- Verifying response properties.
- Checking whether response data is an array or object.
- Validating product and user information.
- Checking response time.
- Saving generated IDs and authentication tokens.
- Verifying successful cart creation, updates, and deletion.

Example test script:

```javascript
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});

pm.test("Response contains products", function () {
    var jsonData = pm.response.json();
    pm.expect(jsonData).to.have.property("products");
    pm.expect(jsonData.products).to.be.an("array");
});
```

## 8. How to Run the Project

1. Install and open Postman.
2. Import the `E-Commerce CRUD Automation - DummyJSON.postman_collection.json` file.
3. Create a Postman environment.
4. Add the `base_url` variable with the value `https://dummyjson.com`.
5. Select the created environment.
6. Open the Authentication folder and execute the Login request first.
7. Execute the remaining requests in the collection.
8. Check the response status, response body, and automated test results.
9. Use the Collection Runner to execute the requests and view the overall test results.

**Note:** Requests that depend on generated IDs or authentication tokens should be executed after their corresponding creation or login requests.

## 9. Important Note About DummyJSON

DummyJSON is a public testing API. Operations such as creating, updating, and deleting products or carts simulate database changes and return responses for testing purposes. They do not permanently modify the original server database.

Therefore, this project demonstrates API testing and automation rather than a live e-commerce application with persistent data.

## 10. Learning Outcomes

- Understanding REST API architecture and HTTP methods.
- Performing CRUD operations using Postman.
- Writing automated test scripts using JavaScript.
- Working with JSON request and response data.
- Understanding authentication and token handling.
- Performing positive and negative API testing.
- Using environment variables for dynamic API testing.

## 11. Conclusion

This project provides practical experience in API testing and automation using Postman. It demonstrates how different REST API endpoints can be tested through automated scripts and how API responses can be validated efficiently.

The project helped develop an understanding of CRUD operations, authentication, response validation, environment variables, and automated software testing using a public E-Commerce API.
