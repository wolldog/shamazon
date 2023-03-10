# Shamazon

## Description

Shamazon provides the backend functionality for an e-commerce website. The application enables you to interact with a MySQL database using Express APIs and Sequelize to select, create, update and delete items from your product cataloge.

### [Shamazon Demo](https://user-images.githubusercontent.com/110208272/220834665-682e2cb5-fbf5-42c9-8434-c3928fe5cccf.mp4)

## Table of Contents
- [Installation](#installation)
- [Usage](#usage)
  - [Parameters](#parameters)
  - [Select](#select)
  - [Create](#create)
  - [Update](#update)
  - [Delete](#delete)
- [Tests](#tests)
- [Questions](#questions)

## <a name="installation"></a> Installation

The application requires Node.js and MySQL to be installed on your local machine. Clone the project folder from GitHub to your local machine, log into MySQL and run `source schema.sql` from the /db folder to create the database.

Run `npm install` to install the dependancies; Express.js, MySql2, Sequelize and DotEnv. Modify env.EXAMPLE to include your MySQL username and password and rename the file to .env. Seed the database using `npm run seed`. You are ready to go!


## <a name="usage"></a> Usage

Run `npm start` to start the server. The server will start on PORT 3001 unless an alternative is supplied in .env.

Shamazon provides routes to select all, select by ID, create, update and delete for each of the three tables; category, product and tag.

### <a name="parameters"></a>Parameters

- **PORT**: required (default 3001)
- **tablename**: required (categories, products or tags)
- **id**: optional for select (not specifying an id will return all), required for update and delete. 

All available routes can be imported into Insomnia using the shamazon.json supplied in /routes.

### <a name="select"></a>Select

`GET http://localhost:{PORT}/api/{tablename}/{id}`

Example responses:

**Category**

```json
{
  "id": 1,
  "category_name": "Shirts",
  "products": [
    {
      "id": 1,
      "product_name": "Plain T-Shirt",
      "price": 15,
      "stock": 14,
      "category_id": 1
    }
  ]
}
```

**Product**

```json
{
 "id": 5,
 "product_name": "Cargo Shorts",
 "price": 30,
 "stock": 22,
 "category_id": 2,
 "category": {
  "id": 2,
  "category_name": "Shorts"
 },
 "product_tags": [
  {
   "id": 3,
   "tag_name": "blue",
   "product_tag": {
     "id": 12,
     "product_id": 5,
     "tag_id": 3,
     "productId": 5,
     "tagId": 3
   }
  }
 ]
}
```

**Tag**
```
{
"id": 2,
"tag_name": "pop music",
"tagged_products": [
 {
  "id": 4,
  "product_name": "Top 40 Music Compilation Vinyl Record",
  "price": 13,
  "stock": 50,
  "category_id": 3,
  "product_tag": {
   "id": 10,
   "product_id": 4,
   "tag_id": 2,
   "productId": 4,
   "tagId": 2
   }
  }
 ]
}
```
### <a name="create"></a>Create

`POST http://localhost:{PORT}/api/{tablename}`

Examples of expected input

**Category**
```
{
 "category_name": "Books"
}
```
**Product**
```
{
 product_name: "Harry Potter - Goblet of Fire",
 price: 25.99,
 stock: 45,
 catagory_name: 6,
 tagIds: [9]
}
```   
**Tag**
```
{
 "tag_name": "fantasy"
}
```
### Update

`PUT http://localhost:{PORT}/api/{tablename}/{id}`

Examples of expected input:

**Category**
```
{
 "category_name": "Childrens books"
}
```
**Product**
```
{
 product_name: "Harry Potter - Chamber of Secrets",
 price: 30.00,
 stock: 40,
 tagIds: [9, 3]
}
```   
**Tag**
```
{
 "tag_name": "fiction"
}
```

### Delete  

`DELETE http://localhost:{PORT}/api/{tablename}/{id}`

## <a name="demo-video"></a>Shamazon Demo

https://user-images.githubusercontent.com/110208272/220834665-682e2cb5-fbf5-42c9-8434-c3928fe5cccf.mp4

## <a name="license"></a>License

N/A

## <a name="tests"></a>Tests

N/A

## <a name="questions"></a>Questions

  If you have questions regarding the Shamazon application,
  you can contact me directly by email at lydiawallis@live.co.uk or reach out
  to me on GitHub at https://www.github.com/wolldog.

