# README For This Project Management Tool App

wifi password for harborside 5:
  92214harborside

## STEP ONE: READ THROUGH THIS README. FOLLOW THE INSTRUCTIONS

This repository demonstrates the usage of sequelize within an express application.

The implemented logic is a simple task tracking tool.

1. create a database called projects_db

`mysql -u root`

`create database projects_db;`

2. Adjust the `config/config.json` to fit your environment.

3. install modules in package.json

`npm install`

4. install sequelize cli globally to be able to run migrations on your computer:

`npm install -g sequelize-cli`

5. run your migrations to create your tables

`sequelize db:migrate`

6. start up the app

`nodemon start`

if you don't have nodemon

`npm start`

7. run the migrations in the app by using:

`sequelize db:migrate`

8. then in the browser go to http://localhost:3000

9. Want to create a migration:

`sequelize migration:create create-<table name here>`

edit the migration file

to run the migration file:

`sequelize db:migrate`

You'll still have to make the model file

10. curious of all the commands you can do with sequelize cli?

go here: https://github.com/sequelize/cli

11. curious of all the sequelize relationships:

http://docs.sequelizejs.com/en/latest/docs/associations/

12.

In order to associate the models with each other, we changed the models like this:

```js
// task.js
// ...
classMethods: {
  associate: function(models) {
    Task.belongsTo(models.User);
  }
}
// ...
```

```js
// user.js
// ...
classMethods: {
  associate: function(models) {
    User.hasMany(models.Task)
  }
}
// ...
```
