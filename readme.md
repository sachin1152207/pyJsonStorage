# pyJsonStorage Documentation

## Overview
pyJsonStorage is a Python package designed to implement basic database functionalities using JSON (JavaScript Object Notation). It provides various features for managing structured data efficiently.

## Features
- **Database Creation**: Easily create new databases using JSON files.
- **Row Operations**: Perform operations like inserting, updating, and deleting rows within the database.
- **JSON Integration**: Utilize the JSON module for seamless management of JSON files.
- **Schema Management**: Define and manage schemas for structured data storage.
- **Querying**: Retrieve data from the database using custom queries.
- **Error Handling**: Implement robust error handling mechanisms for data integrity and consistency.
- **Concurrency Control**: Manage concurrent access to the database to prevent data corruption.

## Installation
You can install pyJsonStorage using pip:
```bash
pip install pyJsonStorage
```
``` bash
from package import pyJsonStorage

# Initialize pyJsonStorage
storage = pyJsonStorage(filePath="your_file_path.json", intent=4)

# Create a new table
storage.createTable(tableName="your_table_name", tableSchema={"column1": "STRING", "column2": "INTEGER"})

# Insert rows into the table
storage.insertRow(tableName="your_table_name", rows=[["data1", 123], ["data2", 456]])

# Fetch one row
storage.fetchOne(filter=("column1", ["data1"]), tableName="your_table_name", field=["column1", "column2"])

# Fetch all rows
storage.fetchAll(tableName="your_table_name", field=["column1", "column2"])

# Update one row
storage.updateOne(filter=("column1", "data1"), newData={"column2": 789}, tableName="your_table_name")

# Delete one row
storage.deleteOne(filter=("column1", "data1"), tableName="your_table_name")

# Delete many rows
storage.deleteMany(filter=("column1", ["data1", "data2"]), tableName="your_table_name")

# Save changes
storage.save()
```
## Methods

- `createTable(tableName:str, tableSchema:dict) -> str`: Create a new table with the specified name and schema.
- `insertRow(tableName:str, rows:list) -> str`: Insert rows into the specified table.
- `fetchOne(filter:tuple, tableName:str, field:list=[]) -> list`: Fetch one row from the table based on the specified filter conditions.
- `fetchAll(tableName:str, field:list=[]) -> list`: Fetch all rows from the table based on the specified field.
- `updateOne(filter:tuple, newData:dict, tableName:str, commit:bool=False) -> str`: Update one row in the table with new values.
- `deleteOne(filter:tuple, tableName:str, commit:bool=False) -> str`: Delete one row from the table based on the specified filter conditions.
- `deleteMany(filter:tuple, tableName:str, commit:bool=False) -> str`: Delete multiple rows from the table based on the specified filter conditions.
- `save() -> bool`: Save the changes made to the database.


## Class: pyJsonStorage

### Description
The `pyJsonStorage` class provides methods for managing JSON-based databases.

### Constructor
#### `__init__(filePath:str, intent:int = 4)`
- **Parameters**:
  - `filePath (str)`: File path of the JSON file. If not existent, a new file will be created.
  - `intent (int)`: Intent level for JSON formatting. Default is 4.

### Methods

#### `createTable(tableName:str, tableSchema:dict) -> str`
- **Description**: Create a new table with the specified name and schema.
- **Parameters**:
  - `tableName (str)`: The name of the table to be created.
  - `tableSchema (dict)`: A dictionary defining the schema of the table.
- **Returns**: A status message indicating the result of the table creation.

#### `insertRow(tableName:str, rows:list) -> str`
- **Description**: Insert rows into the specified table.
- **Parameters**:
  - `tableName (str)`: The name of the table where rows will be inserted.
  - `rows (list)`: A list of lists containing data for each row.
- **Returns**: A status message indicating the result of the row insertion.

#### `fetchOne(filter:tuple, tableName:str, field:list=[]) -> list`
- **Description**: Fetch one row from the table based on the specified filter conditions.
- **Parameters**:
  - `filter (tuple)`: A tuple representing the filter condition.
  - `tableName (str)`: The name of the table from which to fetch the row.
  - `field (list)`: A list of column names to be included in the fetched row.
- **Returns**: A list of dictionaries representing the rows that satisfy the filter condition.

#### `fetchAll(tableName:str, field:list=[]) -> list`
- **Description**: Fetch all rows from the table based on the specified field.
- **Parameters**:
  - `tableName (str)`: The name of the table from which to fetch the row.
  - `field (list)`: A list of column names to be included in the fetched row.
- **Returns**: A list of dictionaries representing the rows that satisfy the filter condition.

#### `updateOne(filter:tuple, newData:dict, tableName:str, commit:bool=False) -> str`
- **Description**: Update one row in the table with new values.
- **Parameters**:
  - `filter (tuple)`: A tuple representing the filter condition.
  - `newData (dict)`: A dictionary containing new values for the row.
  - `tableName (str)`: The name of the table from which to remove the rows.
  - `commit (bool)`: If True, the changes will be saved to the JSON file.
- **Returns**: A status message indicating the result of the operation.

#### `deleteOne(filter:tuple, tableName:str, commit:bool=False) -> str`
- **Description**: Delete one row from the table based on the specified filter conditions.
- **Parameters**:
  - `filter (tuple)`: A tuple representing the filter condition.
  - `tableName (str)`: The name of the table from which to remove the rows.
  - `commit (bool)`: If True, the changes will be saved to the JSON file.
- **Returns**: A status message indicating the result of the operation.

#### `deleteMany(filter:tuple, tableName:str, commit:bool=False) -> str`
- **Description**: Delete multiple rows from the table based on the specified filter conditions.
- **Parameters**:
  - `filter (tuple)`: A tuple representing the filter condition.
  - `tableName (str)`: The name of the table from which to remove the rows.
  - `commit (bool)`: If True, the changes will be saved to the JSON file.
- **Returns**: A status message indicating the result of the operation.

#### `save() -> bool`
- **Description**: Save the changes made to the database.
- **Returns**: True if the changes were successfully saved, otherwise False.


## Authors

- [@sachin1152207](https://github.com/sachin1152207)

