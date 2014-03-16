ToDoListAPI
===========

This is a REST API for a simple ToDo List.
This project is done using SLIM PHP Micro Framework+ Apache +PHP + MySQL

Configuration
-------------
Database: "db_dmp/to_do_list.sql"
MySQL-PHP connection: "include/config.php"

Request
--------
<table>
 <tr>
   <th>URL</th>
   <th>Method</th>
   <th>Parameters</th>
   <th>Description</th>
 </tr>
 <tr>
  <td>/register</td>
  <td>POST</td>
  <td>name,email,password</td>
  <td>User Registration</td>
 </tr>
 <tr>
  <td>/login</td>
  <td>POST</td>
  <td>email,password</td>
  <td>User Login</td>
 </tr>
 <tr>
  <td>/tasks</td>
  <td>POST</td>
  <td>task</td>
  <td>To Create a New Task</td>
 </tr>
 <tr> 
  <td>/tasks</td>
  <td>GET</td>
  <td></td>
  <td>Fetching All Tasks</td>
 </tr>
 <tr>
  <td>/tasks/:id</td>
  <td>GET</td>
  <td></td>
  <td>Fetching A Single Task</td>
 </tr>
 <tr>
  <td>/tasks/:id</td>
  <td>PUT</td>
  <td></td>
  <td>Updating a Single Task</td>
 </tr>
 <tr>
  <td>/tasks/:id</td>
  <td>DELETE</td>
  <td>task,status</td>
  <td>Delete a Single Task</td>
 </tr>
</table>

Response
---------
Upon the successful registration the following json response will be issued.<br>
<pre>{
    "error": false,
    "message": "You are successfully registered"
}</pre>

If the request is missing mandatory parameters the following json will be issued.
<pre>{
    "error": true,
    "message": "Required field(s) email, password is missing or empty"
}</pre>

On successful login the following json will be issued.
<pre>{
    "error": false,
    "name": "Peru",
    "email": "perakka@gmail.com",
    "apiKey": "940bb12af8d7b040876f60f965c5be6d",
    "createdAt": "2014-01-07 23:38:35"
}</pre>

If the credentials are wrong, you can expect the following json.
<pre>{
    "error": true,
    "message": "Login failed. Incorrect credentials"
}</pre>

On successful creation of new task following json will be issued. If you got this json, you can see new row inserted in tasks and user_tasks tables.
<pre>{
    "error": false,
    "message": "Task created successfully",
    "task_id": 1
}</pre>
Getting All ToDos
------------------

<pre>{
    "error": false,
    "tasks": [
        {
            "id": 1,
            "task": "Buy A Book",
            "status": 0,
            "createdAt": "2014-01-08 23:35:45"
        },
        {
            "id": 2,
            "task": "Click the Play",
            "status": 0,
            "createdAt": "2014-01-08 23:56:52"
        }
    ]
}</pre>
