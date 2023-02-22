# shamazon

## Description

Shamazon provides the backend functionality and product database for an e-commerce website.

## Installation

The application requires Node.js and MySQL to be installed on your local machine. Clone the project folder from GitHub to your local machine, log into MySQL and run `source schema.sql` from the /db folder to create the database.

Run `npm install` to install the dependancies; Express.js, MySql2, Sequelize and DotEnv. Modify env.EXAMPLE to include your MySQL username and password and rename the file to .env. Seed the database using `npm run seed`. You are ready to go!


## Usage

Run `npm start` to start the server. The server will start on PORT 3001 unless an alternative is supplied in .env.

Shamazon provides routes to select all, select by ID, create, update and delete for each of the three tables; category, product and tag

All available routes can be imported into Insomnia using the shamazon.json supplied in /routes.


### Shamazon Demo

TODO: ADD DEMO VIDEO

## License

N/A

## Tests

N/A

## Questions

  If you have questions regarding the Shamazon application,
  you can contact me directly by email at lydiawallis@live.co.uk or reach out
  to me on GitHub at https://www.github.com/wolldog.


