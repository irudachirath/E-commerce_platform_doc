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
- Order management: The platform allows Customers to place orders, manage their payments and also manage delivery method.
- Analytics: The platform provides a variety of reports to customers. They can get full detailed report of their order history and also user can get details of each order

### Admin Functionalities

- Product management: The platform allows Admins to create and manage products, including their variants, categories, and inventory.
- Analytics: The platform provides a variety of reports to help administrators to track the performance of their e-commerce business like sales report.

# Quick Links
Edit This!!!!!!!!!!!!

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
- [Checkout and Payment](#Checkout-and-Payment)
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

2. Utilize a MySQL client, such as the MySQL Workbench (recommended) or the MySQL command line client. Navigate to the "database" directory, and execute the `G32_Complete_Database.sql` script. This action will initialize your database, incorporating all requisite stored procedures, functions, views, triggers, and indexes. Additionally, it will populate the database with preliminary sample data.

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

## Requirements

Our project depends on several important Dependencies that provide various functionalities and services to help us develop our application. By utilizing these packages, we can take advantage of their various functionalities and services to make our application more efficiently and effectively. Rather than that there are some Dev-Dependencies used in this project to enhance the developer experience. All the Dependencies used in our project are listed below.

### Front End Dependencies

#### Dependencies
- emotion/react : ^11.11.1,
- emotion/styled : ^11.11.0,
- mui/icons-material : ^5.14.15,
- mui/material : ^5.14.15,
- testing-library/jest-dom : ^5.17.0,
- testing-library/react : ^13.4.0,
- testing-library/user-event : ^13.5.0,
- axios : ^1.5.1,
- js-cookie : ^3.0.5,
- react : ^18.2.0,
- react-dom : ^18.2.0,
- react-router-dom : ^6.16.0,
- react-scripts : 5.0.1,
- react-slick : ^0.29.0,
- slick-carousel : ^1.8.1,
- web-vitals : ^2.1.4

#### Dev-Dependecies
- babel/plugin-proposal-private-property-in-object : ^7.21.11

### Back End Dependencies

#### Dependencies
- bcrypt : ^5.1.1,
- body-parser : ^1.20.2,
- cors : ^2.8.5,
- dotenv : ^16.3.1,
- express : ^4.18.2,
- express-async-errors : ^3.1.1,
- express-session : ^1.17.3,
- jsonwebtoken : ^9.0.2,
- mysql2 : ^3.6.1,
- uuid : ^9.0.1

#### Dev-Dependecies
- nodemon : ^3.0.1

## Developer Guide

### Entity-Relationship (ER) Diagram

![alt text](https://github.com/irudachirath/E-commerce_platform_doc/blob/main/ER_Diagram_v2.0.png?raw=true)

# User Guide

Welcome to our e-commerce platform, where your shopping experience is our top priority. This guide is designed to provide a seamless introduction and ensure you make the most of the platform's features.

## Getting Started

To embark on your shopping journey, you'll first need to navigate to our homepage.Here, you will find a navigation bar with some buttons such as "HOME", "SHOP", "CATEGORIES", "CART", "SIGN UP" and "LOGIN". Additionally, you'll find a variety of product categories are displayed, such as consumer electronics and toys. Clicking on any of these categories will take the user to a page showcasing all the products available in that category. There will be all the available products in the shop there in the homepage below the categories.

## Browsing Products

Our platform provides an intuitive shopping experience. Whether you have a particular product in mind or just wish to browse, the search bar is your starting point. Simply type in keywords or specific product names to refine your search. For those who prefer a more exploratory approach, our homepage showcases main categories and all the sub-categories. Clicking on any category will give you a more in-depth view of all the products in the selected category.

Venturing further, clicking on an individual product will navigate you to its dedicated page. Here, not only are you presented with a detailed description explaining the product's features and benefits, but you'll also find an array of available variants. Each variant is uniquely represented, allowing for an informed choice. Once a decision is made, you can effortlessly add your chosen variant to the cart, setting the stage for purchase.

## Making a Purchase

Once you've settled on a product, specify the desired quantity and click on the "Add to Cart" button. When you're ready to finalize your purchase, head to the cart icon located on the top right of the screen to proceed to Checkout option. Here, you'll provide necessary shipping and payment details. After ensuring all details are accurate, simply confirm your order.

## Managing Your Account

Your personal dashboard is accessible by logging into your account using the "Login" button or by registering as a registered user using the "Sign Up" on the navigation panel on the top of the screen. This space is designed to give you control over various aspects of your account. From account creating to viewing your order history. You can log out from your account anytime using the "Log Out" button located in the same space.

Edit This!!!!!!!!!!!!!!!!!!!!!!!!!!!!!
# Analytics

For those with administrative privileges, an "Admin" button is available in the navigation bar post-login. This feature grants access to several critical reports and analytics:

- Quarterly Sales Report: Review the sales data for any given year, broken down quarterly.
- Top-selling Products: Discover which products garnered the most sales during a specified period.
- Most Ordered Product Category: Identify the product categories that are leading in order volume.
- Product Interest Analysis: Given any product, determine the time frames when it attracted the most attention or interest.
- Customer - Order Report: Gain insights into individual customer order patterns and preferences.