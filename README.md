<h1 align = "center"> Single Vendor E-Commerce Platform - C </h1>
<p align="center">
    <picture>
      <source 
        srcset="https://firebasestorage.googleapis.com/v0/b/e-commerce-3356b.appspot.com/o/Banner.png?alt=media&token=73571f95-149f-4691-8d53-26fb117b56ee&_gl=1*jjsjus*_ga*NjM3NzczMzI4LjE2OTc3MzU5ODI.*_ga_CW55HF8NVT*MTY5ODY3MTQ1OS4yMy4xLjE2OTg2NzE1NTMuNjAuMC4w"
        media="(prefers-color-scheme: dark)"
      />
      <img 
        src="https://firebasestorage.googleapis.com/v0/b/e-commerce-3356b.appspot.com/o/Banner.png?alt=media&token=73571f95-149f-4691-8d53-26fb117b56ee&_gl=1*jjsjus*_ga*NjM3NzczMzI4LjE2OTc3MzU5ODI.*_ga_CW55HF8NVT*MTY5ODY3MTQ1OS4yMy4xLjE2OTg2NzE1NTMuNjAuMC4w" 
        alt="C-Store Project Cover Image"
        width="800"
       />
    </picture>
  </p>

In this Project We implement a database design for a single vendor e-commerce platform for the company "C", a local chain retailer in Texas. We develop a simple UI to demonstrate All functionalities of database. Following features are implemented in this project:

### Customer Functionalities

- Shopping: The platform provide Customers to browse all the products, filter product by some attributes and add products to the cart if they wish to purchase.
- Order management: The platform allows Customers to place orders, manage their payments and also manage delivary method.
- Reporting: The platform provides a variety of reports to customers. They can get full detailed report of their order history and also user can get details of each order

### Admin Functionalities

- Product management: The platform allows Admins to create and manage products, including their variants, categories, and inventory.
- Reporting: The platform provides a variety of reports to help administrators to track the performance of their e-commerce business like sales roport.

# Quick Links

[Installation Guide](#Installation-Guide)

- [Implementation Details](#implementation-details)
- [Getting Started](#getting-started)
- [Configuration of Initial Database](#configuration-of-initial-database)

  - [Overview](#overview)
  - [Tables](#tables)
  - [Column Identifiers](#column-identifiers)
  - [Data Entries](#data-entries)
  - [Sample Table in CSV](#sample-table---productcsv)
  - [Table Relations](#table-relations)
  - [Configuration of environmental variables](#configuration-of-env-file)

- [Requirments](#requirments)

[Developer Guide](#Developer-Guide)

- [Entity-Relationship (ER) Diagram](<#Entity-Relationship(ER)Diagram>)
- [Project Structure](#Project-Structure)

[User Guide](#User-Guide-And-How-To-Instructions)

- [Getting Started](#Getting-Started)
- [Browsing and Shopping](#Browsing-and-Shopping)
- [Checkout and Paymen](#Checkout-and-Payment)
- [Managing Your Account](#Managing-Your-Account)
- [Analytics](#Analytics)
- [Contacting Support](#Contacting-Support)

[About](#about)

# Installation Guide

## Implementation Details

- This project is using a SQL database to manage data.
- This Project uses API to interact with the UI and the database.
- Front End is developed using React
- API is developed using NodeJS (Express)
- According to the project's specifications, an Object-Relational Mapping (ORM) is not used at any point. Instead, the project exclusively utilizes standard SQL queries for all database interactions.
- Developed using NodeJS v18.17.1

## Getting started

- Required Softwares
  - MySQL Workbench 8
  - NodeJS v18.17.1 or higher (version updates are not recommended)
  - Prefered Code editor that can run JavaScript

To get started with the platform, follow these steps :

1.  Clone this repository.
    plaintext
    https://github.com/PasanMadhuranga/Ecommerce-Platform-G32

2.  Open MySQL workbench (Recommended) or MySQL command line client. Go to the databse_creation Folder and run the databsev1.0.sql file. This will create your database and fill it with sample data.

3.  Open a new Terminal from the cloned directory and cd in to the server directory.

    ```plaintext
    cd server
    ```

    Install the dependencies using following command. (Activate the Virutal Environment if you are using one. It's recommended to use one.)

    ```plaintext
    npm i
    ```

    Start the server using following command

    ```plaintext
    npm start
    ```

4.  create .env file inside the server directory including following environmental variables.(You are supposed to update variable values according to your sql environment. You can simply copy the text below, modify it and save at the specified path as a .env file. Also you can fill the .env.example according to your data and remove the .example part).

    - JWT_SECRET and JWT_REFRESH_SECRET should be strong and uncommon for security reasons. (Recommend random strings which has about 64 characters)

    ```dotenv
    DB_PASSWORD=<MySQL Password here>
    DB_PORT=<MySQL Port here>
    JWT_SECRET=<Create a powerful JWT secret key for access token>
    JWT_REFRESH_SECRET=<Create a powerful JWT secret key for refresh token>
    ```

5.  Go back to the previous directory and go to the client directory.

    ```plaintext
    cd ..\client
    ```

    Then install the dependencies using following command.

    ```plaintext
    npm i
    ```

    Start the React app using following command.

    ```plaintext
    npm start
    ```

6.  Now website will automatically open with your web browser.

## Configuration of Initial Database

### Overview

Everything you have to modify to create the initial database you wish to have is located inside /dbInitialData/ directory.

- database_relations.sql holds 'ALTER' queries which creates the relations between tables of the database.
- All the .csv files, each represents a table in the initial database.
- .env file (should be created by you as mentioned) contains environmental variables related to your MySQL environment.

### Tables

Every .csv file will generate a separate table in the database.

Table name will be the same as the csv file's name.

- Ex - product.csv creates a table in the database called product. So you can create or rename the csv files as per your requirement.

> [!Important]
>
> - While altering the inital data as they wish according to the data constraints is recommended for any user, creating,renaming or deleting tables via creating,renaming or deleting the respective `.csv` files is only meant to be done by advanced users since the project depends on the current database schema despite being independant of the dummy data.

You can either use something like Microsoft Excel or a plain text editor like Notepad for the purpose of creation and editing of CSV files.

**Make sure to use double quotes(") as the quotechar and comma(,) as the delimiter. Otherwise the project will fail to initiate the database properly.**

- If you are editing csvs' in Excel make sure that the delimiter and quotechar is set as specified. If you are using a text editor, you have to explicitly use the quotechar and delimiter wherever required. Using Excel is the preffered way.

### Column Identifiers

In each coloumn name, only the first word should be the column identifier. There after you have to specify the Data type starting from the next word.

_Do Not enter anything other than the "\<column_identifier\> \<data type\>"._

### Data Entries

Fill the CSV file with records in the regular way. But data have to be in accordance with the data type of the respective column.

### Sample Table - product.csv

#### Table view

| product_id INT | title VARCHAR(255) | description TEXT          | weight DECIMAL(10, 2) | category_id INT | product_image TEXT |
| -------------- | ------------------ | ------------------------- | --------------------- | --------------- | ------------------ |
| 101            | Samsung galaxy S21 | Samsung Galaxy S21, 128GB | 0.35                  | 3               | /assets/s21u.jpeg  |
| 202            | Dennim Jeans       | Classic denim jeans       | 0.6                   | 6               | /assets/jean.jpeg  |

#### Text View

csv
product_id INT,title VARCHAR(255),description TEXT,"weight DECIMAL(10,2)",category_id INT,product_image TEXT
101,Samsung galaxy S21,"Samsung Galaxy S21, 128GB",0.35,3,/assets/s21u.jpeg
202,Dennim Jeans,Classic denim jeans,0.6,6,/assets/jean.jpeg

### Table relations

You have to write ALTER SQL queries for the referencing inside dbInitialData/database_relations.sql.

Keep an empty line between each SQL query.
You can add comments if you want to. But it is recommended to avoid comments.

Ex -  
 sql
ALTER TABLE product
ADD CONSTRAINT pk_product_id
PRIMARY KEY (product_id);

    ALTER TABLE variant
    ADD CONSTRAINT pk_variant_id
    PRIMARY KEY (variant_id);

### Configuration of .env file.

- Refer the [Getting Started](#getting-started) segment of this document.

## Requirments

### Python Package Dependencies

These are essential Python libraries and packages that your project relies on to operate successfully. They provide various functionalities and services to help you develop your application. Below is a list of these packages.

- ansi2html
- blinker
- cachelib
- certifi
- charset-normalizer
- click
- colorama
- dash
- dash-core-components
- dash-html-components
- dash-table
- Flask
- Flask-Session
- idna
- importlib-metadata
- itsdangerous
- Jinja2
- MarkupSafe
- mysql-connector-python
- nest-asyncio
- numpy
- packaging
- pandas
- plotly
- protobuf
- python-dateutil
- python-dotenv
- pytz
- requests
- retrying
- six
- tenacity
- typing_extensions
- tzdata
- urllib3
- Werkzeug
- zipp

# Developer Guide

## Entity-Relationship (ER) Diagram

<p align="center">
    <picture>
      <source 
        srcset="assets/ERdiagram.png"
        media="(prefers-color-scheme: dark)"
      />
      <img 
        src="assets/ERdiagram.png" 
        alt="ER Diagram"
        height ="600"
       />
    </picture>
  </p>

## Project Structure

- The project structure is the organization of files and directories in our e-commerce platform project. It's essential for maintaining a clean, understandable, and scalable codebase.

- All the csv files are included the dbinitialData folder such as cart.csv,category.csv,product.csv . In order to create tables.

- All the relasionship among tables in the intial database are included in the database_relations.sql

- A directory for storing static assets such as images, CSS files, and other resources used in the static directory.

- Static directory included category-images,product-images,subcategory-images folders. Images for related functions are included in these files separately. All the styles are included in the style.css file.

- In this requirements.txt file, all the required modules are included

- In templates, this directory holds HTML templates that are used to render web pages.

- The intial database is configured in this darabaseConfig.py file.

- dbaccess.py file contains the functions to communicate with the database using sql queries

# User Guide

## Getting Started

- Creating an Account: To get started with our e-commerce platform, user will need to create an account. Click on the "Sign Up" button on the homepage, and provide user's details, including user's name, email address, and a secure password.

- Logging In: If user already have an account, simply click on the "Log In" button. Enter user's registered email and password to access user's account.

<p align="center">
    <picture>
      <source 
        srcset="assets/registration.png"
        media="(prefers-color-scheme: dark)"
      />
      <img 
        src="assets/registration.png" 
        alt="Login image"
        height="300"
       />
    </picture>
  </p>

## Browsing and Shopping

- Exploring Products: Browse through the our wide range of products by clicking on the various categories displayed on the product page.

       Ex - Electronic products

            Toy products

- Product Details: Click on a product to view its details. This includes the product's name, description, price, and any available variants. User can also see images of the product.

- Adding to Cart: When user has found an item user would like to purchase, click the "Add to Cart" button. User can specify the quantity and select variants, if applicable.

- Shopping Cart: To review user's selected items, click on the cart icon at the top of the page. Here, user can make any necessary adjustments to user's order.

- Continue shopping : To go to the shopping page again, click on the Continue shopping button.

- go to Checkout: Once user is satisfied with user's selections, click "go to Checkout" to complete user's purchase.

## Checkout and Payment

- Delivery Information: Provide the necessary delivery information, including user's shipping address.

- Payment: Select user's preferred payment method (e.g., cash on delivery, card payment). Enter user's payment details securely.

- Continue to checkout : When user is ready, click "Continue to checkout."

<p align="center">
    <picture>
      <source 
        srcset="assets/checkout.png"
        media="(prefers-color-scheme: dark)"
      />
      <img 
        src="assets/checkout.png" 
        alt="checkout Image"
        height="300"
       />
    </picture>
  </p>

## Managing User's Account

- Logging Out: To log out of user's account, simply click the "Log Out" button. It's important to log out, especially if user is using a shared computer.

## Analytics

- Total Quarterly Sales Over the Years: This section provides information about our total sales for each quarter over the years. It gives user an overview of our sales performance.

- Product Sales Quantities: Here, user can explore data related to product sales quantities. It helps user understand which products are the most popular among our customers.

- Trending Categories: Discover the product categories that are currently trending on our platform. This data can be helpful for making informed shopping decisions.

- Sales Throughout the Year: Get insights into how our sales perform throughout the year. It can help user plan user's shopping based on seasonal trends and discounts.

### sample analytic table

<p align="center">
    <picture>
      <source 
        srcset="assets/sample.png"
        media="(prefers-color-scheme: dark)"
      />
      <img 
        src="assets/sample.png" 
        alt="Analytics report sample"
        height="400"
       />
    </picture>
  </p>

## Contacting Support

- Contact Us: If user encounter any issues or have questions about our products or services, user can reach out to our customer support team. Click on the "Contact Us" link to find our contact details.

- Terms and conditions : Click on the "Terms and Conditions" link to read about terms and conditions.

That's it! User is now ready to explore and shop on our e-commerce platform. If user has any further questions or need assistance, don't hesitate to reach out to our friendly customer support team. Happy shopping!

# About

This project was created as part of a 2<sup>nd</sup> year university project under the Database Systems module in the Department of Computer Science and Engineering at the University of Moratuwa. Any contributions are welcome!

[Go to the Top](#e-commerce-platform-for-c)
