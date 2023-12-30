---
hide:
  - navigation
---

# MongoDB
## Setup mongo Database standalone

`docker pull mongo`

`docker run -p 27017:27017 --name my-mongodb -v my-mongodb-data:/data/db -d mongo`

For Mongo DB, download [MongoDB Compass](https://www.mongodb.com/products/compass) for graphical UI for interacting with mongoDB:

## Python Mongo DB Drivers:
There are two popular drivers available:

1. PyMongo (Official)
2. MongoEngine (Wrapper over PyMongo, provides Object Mapping similar to SQLAlchemy)

### PyMongo
Repository: [https://github.com/mongodb/mongo-python-driver](https://github.com/mongodb/mongo-python-driver)

Examples:

1. [PyMongo Example](https://www.w3schools.com/python/python_mongodb_insert.asp)
2. [PyMongo Example with FastAPI](https://www.mongodb.com/languages/python/pymongo-tutorial)

### Mongo Engine

A Python Object-Document-Mapper for working with MongoDB

Repository: [https://github.com/MongoEngine/mongoengine](https://github.com/MongoEngine/mongoengine)

Examples:

1. [Mongo Engine Example](http://docs.mongoengine.org/tutorial.html)

### Comparison

[PyMongo vs Mongo Engine Comparison](https://www.mongodb.com/compatibility/mongoengine-pymongo)

### Python FastAPI with pymongo
If you are using Python FastAPI, you can go with pymongo as there are already models defined for FastAPI. 

[Pymongo Tutorial with FastAPI](https://www.mongodb.com/languages/python/pymongo-tutorial) | [Github Repo](https://github.com/mongodb-developer/pymongo-fastapi-crud)

## Python Unit Tests and Mocking Options
1. [https://github.com/schireson/pytest-mock-resources](https://github.com/schireson/pytest-mock-resources)
2. [https://github.com/mdomke/pytest-mongodb](https://github.com/mdomke/pytest-mongodb)
3. [https://github.com/mongomock/mongomock](https://github.com/mongomock/mongomock)

### References
1. [https://stackoverflow.com/questions/42239241/how-to-mock-mongodb-for-python-unittests](https://stackoverflow.com/questions/42239241/how-to-mock-mongodb-for-python-unittests)
2. [https://stackoverflow.com/questions/66223290/mocking-database-calls-in-python-using-pytest-mock](https://stackoverflow.com/questions/66223290/mocking-database-calls-in-python-using-pytest-mock)