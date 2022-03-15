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

After installing the required technologies, the user must also install an application that can test REST APIs. This backend application uses [Insomnia](https://insomnia.rest/) to test the API routes for this code. 

Then, the user must edit the `.env.Example` file in the main folder where the `server.js` file is located. The file must be renamed to `.env` to properly work with the code. The user and password must also be edited to reflect the user's username (for some users, "root" is usually their username) and password for their MySQL access. 

After installing the required technologies and application to test REST APIs, the user can begin using the program. To begin, the user must first source the database by logging into their SQL by running `mysql -u root -p` in the terminal. After logging in, the user can run `source db/schema.sql` to use the correct database. Then, the user can type `quit` to exit the MySQL console. 

After selecting the database, the user has to seed the data into the database by running `npm run seed`. The user will see the specific data being run into the database in the terminal. 

After seeding the database, the application can be run by using this command in the terminal `npm start`. If it does not work, `node server.js` will run the server. The user will know the server is running if the following console log shows in the terminal: `App listening on port 3001`.

### Walkthrough video 
* [How to source schema from MySQL and to seed the database from the command line](https://drive.google.com/file/d/18Zbvash4Hc4WYKHcYUIyPknwTOS7hQ_v/view)
![Walkthrough schema, seeding, and start](./assets/ECBackEndInstallation.gif)


## Usage
The following bullets show how to use the GET, POST, PUT, and DELETE routes on Insomnia

* GET all categories, products, or tags

    * To view all categories, the user must make a GET request and use the following line of code before clicking SEND:
    `http://localhost:3001/api/categories`

    * To view all products, the user must make a GET request and use the following line of code before clicking SEND:
    `http://localhost:3001/api/products`

    * To view all tags, the user must make a GET request and use the following line of code before clicking SEND: 
    `http://localhost:3001/api/tags`

    * [Walkthrough Video to GET all](https://drive.google.com/file/d/1g5_O_BgtCofZk4UMQFqZdmNsDH9Wa1zu/view)
    ![Walkthrough of GET all](./assets/ECBackEndGETAll.gif)

* GET one category, product, or tag by id 

    * To view a specific category by id, the user must make a GET request then use this line of code before clicking SEND[^1]
    `http://localhost:3001/api/categories/id#`

    * To view a specific product by id, the user must make a GET request then use this line of code before clicking SEND[^1]
    `http://localhost:3001/api/products/id#`

    * To view a specific tag by id, the user must make a GET request then use this line of code before clicking SEND[^1]
    `http://localhost:3001/api/tags/id#`

    * [Walkthrough video to GET one by id](https://drive.google.com/file/d/1FTRitSH4RSfLN6JVIwh9ld1ftXeDFuEq/view)
    ![Walkthrough video to GET one by id](./assets/ECBackEndGETOne.gif)

* CREATE a category, product, or tag

    * To create a new category, the user must make a POST request with a JSON body and use this line before clicking SEND
    `http://localhost:3001/api/categories`

        * The JSON body must be formatted like this: 
            ```
            {
            "category_name" : "new-category-name"
            }
            ```
        The user can edit inside of the quotation marks of the `new-category-name` to whatever new category they would like to create. 

    * To create a new product, the user must make a POST request with a JSON body and use this line before clicking SEND
    `http://localhost:3001/api/products`

        * The JSON body must be formatted like this: 
            ```
            {
            "product_name": "new-product-name",
            "price": 200.00,
            "stock": 3,
            "tagIds": [1, 2, 3, 4]
            }
            ```
            The user can edit inside of the quotation marks of the `new-product-name` to whatever new product they would like to create. The user will also be able to edit the price, stock, or tagIds by changing the integer value to any number. 

    * To create a new tag, the user must make a POST request with a JSON body and use this line before clicking SEND
    `http://localhost:3001/api/tags`
        * The JSON body must be formatted like this: 
            ```
            {
            "tag_name" : "new-tag-name"
            }
            ```
        The user can edit inside of the quotation marks of the `new-tag-name` to whatever new category they would like to create. 

    * [Walkthrough video to create using the POST route](https://drive.google.com/file/d/1ZgvtcNp8SYQHVk9FoqIo46UA-0Ad1Ak1/view)
    ![walkthrough POST](./assets/ECBackEndCREATE.gif)

* UPDATE a category, product, or tag by id

    * To update an existing category, the user must make a PUT request with a JSON body and use this line before clicking SEND[^1]
    `http://localhost:3001/api/categories/id#`

        * The JSON body should look like this: 
        ```
        {
        "category_name" : "updated-category-name"
        }
        ```
        The `updated-category-name` can be changed to the new name the user wants. 

    * To update an existing product, the user must make a PUT request with a JSON body and use this line before clicking SEND[^1]
    `http://localhost:3001/api/products/id#`

        * The JSON body should look like this: 
            ```
            {
            "product_name": "updated-product-name",
            "price": 200.00,
            "stock": 3,
            "tagIds": [1, 2, 3, 4]
            }
            ```
        The `updated-product-name` can be changed to the new name the user wants, and the price, stock, and tagIds can be changed to a new integer if desired. 

    * To update an existing tag, the user must make a PUT request with a JSON body and use this line before clicking SEND[^1]
    `http://localhost:3001/api/tags/id#`

        * The JSON body should look like this: 
            ```
            {
            "tag_name" : "updated-tag-name"
            }
            ```
        The `updated-tag-name` must be changed to the new name the user wants.

    * [Walkthrough video of updating through the PUT route](https://drive.google.com/file/d/1HKSxoLsxrB8hQgs7KRE9Kbcy9cjYSv_D/view)
    ![Walkthrough PUT](./assets/ECBackEndPUT.gif)

* DELETE a category, product, or tag by id

    * To delete a category by id, the user must make a DELETE request and use this command before clicking SEND[^1]
    `http://localhost:3001/api/categories/id#`

    * To delete a product by id, the user must make a DELETE request and use this command before clicking SEND[^1] 
    `http://localhost:3001/api/products/id#`

    * To delete a tag by id, the user must make a DELETE request and use this command before clicking SEND[^1] 
    `http://localhost:3001/api/tags/id#`

    * [Walkthrough video to delete using the DELETE route](https://drive.google.com/file/d/1ZZIlLKL3sbEujs-OeyH2F4CQD9ssQMwT/view)
    ![Walkthrough DELETE](./assets/ECBackEndDELETE.gif)
    
[^1]: The user must replace `id#` at the end of the command with the specific id number of the category, product, or tag that is meant to be manipulated. 

## Technologies Used
* dotenv
* Express
* MySQL2
* Sequalize
