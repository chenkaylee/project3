# Project 3
## Overview
In this practicum you will modify the database you built for previous projects to adjust them to a key-value in-memory database (Redis). You can reuse the project description, selecting one data structure that makes sense to be implemented as an in-memory store. Finally you will modify your existing codebase to make it work with Node and Redis.

## Format
This work should be completed individually

## Tasks
1. (10 pts) Provide the problem requirements and the conceptual model in UML for your project. You can reuse the one made on previous projects, but describe the functionalities that you selected to be used as an in-memory key-value storage, (e.g. most viewed products, a shopping cart, current logged-in users, etc).
2. (30 pts) Describe the Redis data structures that you are going to use to implement the functionalities you described in the previous point. (example To implement the most viewed products I will use a Redis sorted set with key "mostViewed:userId", product ids as the values and a score of the number of views of the product.). You can use/describe more than one data structure, you will need to implement at least one.
3. (30 pts) The redis commands that you would use to interact with your specific Redis structures. 
Example: I will keep a sorted set with the most viewed products in my application. Therefore I need:
Initialize:
FLUSHALL
Get the list of most viewed items for user duto_guerra:
ZREVRANGE mostViewed:duto_guerra 0 -1
When user duto_guerra visits produc p1234 one more time:
ZINCRBY mostViewed:duto_guerra 1 p1234
etc...
Describe the commands for all your use cases. Make sure to include all CRUD operations

4. (30 pts Optional) Create a basic Node + Express application that let's you create, display, modify and delete at least one Redis data structure from the ones describe in the previous point. No need to have a polished interface, and you can use the code created in class as a starting point, and/or the code you created for previous projects

5. (10pts Optional) Alternative to 4. Create a node script that implements your redis design. See for example this one implementing a basic Caching system with Mongo and Redis https://github.com/john-guerra/nodeMongoRedis_CacheExample
