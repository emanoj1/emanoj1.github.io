---
layout: post
date: 2024-05-16 15:55:00 +1000
title: 10. The Commit method in SQLAlchemy
tag: sqlalchemy
---

What is the purpose of the commit() method in SQLAlchemy?

In SQLAlchemy, the `commit()` method is used to commit the current transaction to the database. 
SQLAlchemy operates within a transactional model, where database operations are grouped into transactions. 
The `commit()` method is responsible for finalizing any changes made within the current transaction, ensuring that they are persisted in the database.  


Here's a basic outline of how it works:  


1. Begin a transaction.
2. Perform database operations (e.g., insert, update, delete).
3. Call `commit()` to commit the transaction, making the changes permanent.
4. Optionally, handle any exceptions that may occur during the transaction and rollback changes if necessary.  


By explicitly calling `commit()`, you ensure that changes are applied atomically; that is, either all changes are committed successfully, 
or none of them are applied (in case of an error or explicit rollback).  


Here's a simplified example of using `commit()` in SQLAlchemy:

```python
from sqlalchemy import create_engine, Column, Integer, String
from sqlalchemy.ext.declarative import declarative_base
from sqlalchemy.orm import sessionmaker

# Create an engine
engine = create_engine('sqlite:///example.db')

# Define a base class for declarative
Base = declarative_base()

# Define a model
class User(Base):
    __tablename__ = 'users'
    id = Column(Integer, primary_key=True)
    name = Column(String)

# Create the schema
Base.metadata.create_all(engine)

# Create a session
Session = sessionmaker(bind=engine)
session = Session()

# Create a new user
new_user = User(name='John Doe')
session.add(new_user)

# Commit the transaction to persist the changes
session.commit()

# Close the session
session.close()
```

In this example, `session.commit()` is called after adding a new user to the session. This commits the transaction and persists the new user record in the database.
