# Shamazon

## Description

Shamazon provides the backend functionality and product database for an e-commerce website. Using Node, MySQL, Sequeli

## Table of Contents
- [Installation](#installation)
- [Usage](#usage)
  - [Parameters](#parameters)
  - [Select](#select)
  - [Create](#create)
  - [Update](#update)
  - [Delete](#delete)
- [Demo video](#demo-video)
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
 product_name: "Basketball",
 price: 200.00,
 stock: 3,
 tagIds: [1, 2, 3, 4]
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
 "category_name": "Books"
}
```
**Product**
```
{
 product_name: "Basketball",
 price: 200.00,
 stock: 3,
 tagIds: [1, 2, 3, 4]
}
```   
**Tag**
```
{
 "tag_name": "fantasy"
}
```

### Delete  

`DELETE http://localhost:{PORT}/api/{tablename}/{id}`

All available routes can be imported into Insomnia using the shamazon.json supplied in /routes.

## <a name="demo-video"></a>Shamazon Demo

TODO: ADD DEMO VIDEO

## <a name="license"></a>License

N/A

## <a name="tests"></a>Tests

N/A

## <a name="questions"></a>Questions

  If you have questions regarding the Shamazon application,
  you can contact me directly by email at lydiawallis@live.co.uk or reach out
  to me on GitHub at https://www.github.com/wolldog.


