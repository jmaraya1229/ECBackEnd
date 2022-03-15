# E-Commerce Back End

## Description
This application uses a functional Express.js API to access a database that can be viewed and can create, update, and delete data using API routes. 

## Table of Contents
* [Installation](#installation)
* [Usage](#usage)
* [Technologies Used](#technologies-used)

## Installation
To begin the installation, the user must ` git clone` this [repo](https://github.com/jmaraya1229/ECBackEnd) into their local machine by using the ssh key located in the green Code button. After cloning, the user can install the required technologies by running `npm install` in their terminal. If the required technologies do not get installed, the user can run the following commands to install them individually: 
* npm install dotenv 
* npm install mysql2 
* npm install sequelize
* npm install express

After installing the required technologies, the user must also install an application that can test REST APIs. This program uses [Insomnia](https://insomnia.rest/) to test the API routes for this code. 

Then, the user must edit the `.env.Example` file in the main folder where the `server.js` file is located. The file must be renamed to `.env` to properly work with the code. The user and password must also be edited to reflect the user's username and password for their MySQL access. 

After installing the required technologies and application to test REST APIs, the user can begin using the program. To begin, the user must first source the database by logging into their SQL by running `mysql -u root -p`in the terminal. After logging in, the user can run `source db/schema.sql` to use the correct database. Then, the user can type `quit` to exit the MySQL console. 

After selecting the database, the user has to seed the data into the database by running `npm run seed`. The user will see the specific data being run into the database in the terminal. 

After seeding the database, the application can be run by using this command in the terminal `npm start`. If it does not work, `node server.js` will run the server. The user will know the server is running if the following console log shows in the terminal: `Listening to port 3001`.

### Walkthrough video 
* How to source schema from MySQL and to seed the database from the command line
![Walkthrough schema and seeding]()


## Usage
The following bullets show how to use the GET, POST, PUT, and DELETE routes on Insomnia

* GET all categories, products, or tags

    * To view all categories, the user must make a GET request and use the following line of code before clicking SEND:
    `https://localhost:3001/api/categories`

    * To view all products, the user must make a GET request and use the following line of code before clicking SEND:
    `https://localhost:3001/api/products`

    * To view all tags, the user must make a GET request and use the following line of code before clicking SEND: 
    `https://localhost:3001/api/tags`

    * Walkthrough Video to GET all
    ![Walkthrough of GET all]()

* GET one category, product, or tag by id 

    * To view a specific category by id, the user must make a GET request then use this line of code[^1] before clicking SEND
    `https://localhost:3001/api/categories/id#`

    * To view a specific product by id, the user must make a GET request then use this line of code[^1] before clicking SEND
    `https://localhost:3001/api/products/id#`, or 

    * To view a specific tag by id, the user must make a GET request then use this line of code[^1] before clicking SEND
    `https://localhost:3001/api/tags/id#`

    [^1]: The `id#` at the end of each line must be replaced by the id number of the item the user is searching for. 

    * Walkthrough video to GET one by id
    ![Walkthrough video to GET one by id]()

* CREATE a category, product, or tag

    * To create a new category, the user must make a POST request with a JSON body and use this line before clicking SEND
    `https://localhost:3001/api/categories`
        The JSON body must be formatted like this: 
        ```
        {
        "category_name" : "new-category-name"
        }
        ```
        The user must edit inside of the quotation marks of the `new-category-name` to whatever new category they would like to create. 

    * To create a new product, the user must make a POST request with a JSON body and use this line before clicking SEND
    `https://localhost:3001/api/products`
    The JSON body must be formatted like this: 
        ```
        {
        "product_name" : "new-product-name"
        "price" : ""
        }
        ```
        The user must edit inside of the quotation marks of the `new-product-name` to whatever new category they would like to create. The user may also edit within the quotation marks for the price if they want to add a price to the product. 

    * To create a new tag, the user must make a POST request with a JSON body and use this line before clicking SEND
    `https://localhost:3001/api/tags`
        The JSON body must be formatted like this: 
        ```
        {
        "tag_name" : "new-tag-name"
        }
        ```
        The user must edit inside of the quotation marks of the `new-tag-name` to whatever new category they would like to create. 

    * Walkthrough video to create using the POST route
    ![walkthrough POST]()

* UPDATE a category, product, or tag by id

    * To update an existing category, the user must make a PUT request with a JSON body and use this line before clicking SEND
    `https://localhost:3001/api/categories/id#`
    The id# must be replaced with the id number of the category that is meant to be updated. 
        The JSON body should look like this: 
        ```
        {
        "category_name" : "updated-category-name"
        }
        ```
        The `updated-category-name` must be changed to the new name the user wants. 

    * To update an existing product, the user must make a PUT request with a JSON body and use this line before clicking SEND
    `https://localhost:3001/api/products/id#`
    The id# must be replaced with the id number of the category that is meant to be updated. 
        The JSON body should look like this: 
        ```
        {
        "product_name" : "updated-product-name"
        }
        ```
        The `updated-product-name` must be changed to the new name the user wants.the other stuff can be updated as well. 

    * To update an existing tag, the user must make a PUT request with a JSON body and use this line before clicking SEND
    `https://localhost:3001/api/tags/id#`
    The id# must be replaced with the id number of the category that is meant to be updated. 
        The JSON body should look like this: 
        ```
        {
        "tag_name" : "updated-tag-name"
        }
        ```
        The `updated-tag-name` must be changed to the new name the user wants.

    * Walkthrough video of updating through the PUT route
    ![Walkthrough PUT]()

* DELETE a category, product, or tag by id

    * To delete a category by id, the user must make a DELETE request and use this command before clicking SEND[^2]
    `https://localhost:3001/api/categories/id#`

    * To delete a product by id, the user must make a DELETE request and use this command before clicking SEND[^2] 
    `https://localhost:3001/api/products/id#`

    * To delete a tag by id, the user must make a DELETE request and use this command before clicking SEND[^2] 
    `https://localhost:3001/api/tags/id#`
    
        The user must replace id# with the specific id number of the tag that is meant to be deleted. 

## Technologies Used
* dotenv
* Express
* MySQL2
* Sequalize
