---
hide:
  - navigation
---

# MongoDB
## Setup mongo Database standalone

`docker pull mongo`

`docker run -p 27017:27017 --name my-mongodb -v my-mongodb-data:/data/db -d mongo`

For Mongo DB, download MongoDB Compass for graphical UI for interacting with mongoDB:

https://www.mongodb.com/products/compass

## Python Mongo DB Drivers:

There are two popular drivers available:
1.  PyMongo (Official)
2.  MongoEngine (Wrapper over PyMongo, provides Object Mapping similar to SQLAlchemy)

### PyMongo

pymongo: https://github.com/mongodb/mongo-python-driver (Official)

PyMongo Example: [https://www.w3schools.com/python/python_mongodb_insert.asp](https://www.w3schools.com/python/python_mongodb_insert.asp)

PyMongo Example with FastAPI: [https://www.mongodb.com/languages/python/pymongo-tutorial](https://www.mongodb.com/languages/python/pymongo-tutorial)

### MongoEngine

A Python Object-Document-Mapper for working with MongoDB

https://github.com/MongoEngine/mongoengine

MongoEngine Example: [http://docs.mongoengine.org/tutorial.html](http://docs.mongoengine.org/tutorial.html)

### PyMongo vs MongoEngine Comparison

[https://www.mongodb.com/compatibility/mongoengine-pymongo](https://www.mongodb.com/compatibility/mongoengine-pymongo)

### Python FastAPI with pymongo
If you are using Python FastAPI, you can go with pymongo as there are already models defined for FastAPI. Below is an example of pymongo with FastAPI:
https://www.mongodb.com/languages/python/pymongo-tutorial
Github Repo: https://github.com/mongodb-developer/pymongo-fastapi-crud

## Python Unit Tests and Mocking Options
1. https://github.com/schireson/pytest-mock-resources
2. https://github.com/mdomke/pytest-mongodb
3. https://github.com/mongomock/mongomock

### References
1. https://stackoverflow.com/questions/42239241/how-to-mock-mongodb-for-python-unittests
2. https://stackoverflow.com/questions/66223290/mocking-database-calls-in-python-using-pytest-mock