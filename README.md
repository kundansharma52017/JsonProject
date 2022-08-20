# JsonProject
Json repository
TITLE OF PROJECT
                           Bootstrap Example
                              Description
Introduction to JsonPowerDB
JsonPowerDB is a Real-time, High Performance, Lightweight and Simple to Use, Rest API based Multi-mode DBMS. JsonPowerDB has ready to use API for Json document DB, RDBMS, Key-value DB, GeoSpatial DB and Time Series DB functionality. JPDB supports and advocates for true serverless and pluggable API development.
In this course the candidate will learn about basics of JsonPowerDB (JPDB) and how to use JPDB for simple database operations. Candidate will learn CRUD and some more important API commands that will be usefull to create a dynamic website or mobile app.

Benefits of using JsonPowerDB

JsonPowerDB (JPDB) is Next Generation, Creative and Disruptive Multi-mode DBMS_ with many USPs.
•	Proprietary algorithm for High Performance CRUD operations. Multiple times faster than popular DBMS.
•	Serverless support for faster development - A UI developer can develop complete dynamic application.
•	DBMS with built in web / application server and embedded caching makes the performance lightning fast.
•	Server side Native NoSQL - best query performance.
•	In-built support to query on multiple JPDB databases.
•	Multi-mode DBMS - Document DB, Key-Value DB, RDBMS support.
•	Schema free - easy to develop and maintain.
•	Web-services API - Can be used with any programming language that has support for HTTP.
•	Enriched by a pluggable API Framework - A developer can develop a pluggable API and plugin into any of our cloud JPDB instance.
•	Standardisation of API development framework makes the development process easy, more readable, and less error prone.
•	Multiple security layer/
•	Nimble, Simple to use, I Memory, Real-time DBMS.
Release History (release of your JsonPowerDB related code on Github)

1. A short Employee Database web form implementing JsonPowerDB.
2. validation form using jsonPowerDB
3. This project is all about basics of JsonPowerDB (JPDB) and how to use JPDB for CRUD operations.
4. JSON Power databse CRUD operation in contribution with Login2Xplore,Bhopal,MP.
5. The Repository contains a simple Application form,Which has the connection to the JsonPowerDB.
6. A Student DB management RESTful web application implementing JSONpowerDB ( NoSQL ).


Table Content
1.Illustrations
2.Scope of functionalities
3.Examples of use
4.Project status
                                 5.Sources
<!DOCTYPE html>
<!--
To change this license header, choose License Headers in Project Properties.
To change this template file, choose Tools | Templates
and open the template in the editor.
-->
<html lang="en">
<head>
<title>Bootstrap Example</title>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<link rel="stylesheet"
href="https://maxcdn.bootstrapcdn.com/bootstrap/3.4.1/css/bootstrap.min.css">
   <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js"></script>
   <script src="https://maxcdn.bootstrapcdn.com/bootstrap/3.4.1/js/bootstrap.min.js"></script>
   <script src="https://login2explore.com/jpdb/resources/js/0.0.4/jpdb-commons.js"></script>
</head>
<body>
<div class="container">
<h2>Vertical (basic) form</h2>
<form id="empForm" method="post">
<div class="form-group">
<span><label for="empId">Employee ID:</label> <label id="empIdMsg">
</label></span>
<input type="text" class="form-control" name="empId" id="empId"
placeholder="Enter Employee ID" required>
</div>
<div class="form-group">
<label for="empName">Employee Name:</label>
<input type="text" class="form-control" id="empName"
placeholder="Enter Employee Name" name="empName">
</div>
<div class="form-group">
<label for="empEmail">Email:</label>
<input type="email" class="form-control" id="empEmail"
placeholder="Enter Employee Email" name="empEmail">
</div>
<input type="button" class="btn btn-primary" id="empSave" value="Save"
onclick="saveEmployee();">
</form>
</div>
    <script>
        $("#empId").focus();
   function validateAndGetFormData() {                                                //validate form data
         var empIdVar = $("#empId").val();
         if (empIdVar === "") {
         alert("Employee ID Required Value");
         $("#empId").focus();
         return "";
        }
        var empNameVar = $("#empName").val();
        if (empNameVar === "") {
        alert("Employee Name is Required Value");
        $("#empName").focus();
        return "";
         }
         var empEmailVar = $("#empEmail").val();
         if (empEmailVar === "") {
         alert("Employee Email is Required Value");
         $("#empEmail").focus();
         return "";
         }
         var jsonStrObj = {
         empId: empIdVar,
         empName: empNameVar,
         empEmail: empEmailVar,
         };
         return JSON.stringify(jsonStrObj);
         }
         
           function resetForm() {
             $("#empId").val("")
             $("#empName").val("");
              $("#empEmail").val("");
              $("#empId").focus();
          }

         function saveEmployee() {
         var jsonStr = validateAndGetFormData();        //validate form data
            if (jsonStr === "")
            {
            return;
           }
           var putReqStr = createPUTRequest("90936861|-31948784479254024|90932362",   // create JPDB request -token ,dbname , rel name....
         jsonStr, "SAMPLE", "EMP-REL");
         alert(putReqStr);
         jQuery.ajaxSetup({async: false});
         var resultObj = executeCommandAtGivenBaseUrl(putReqStr,"http://api.login2explore.com:5577", "/api/iml");     //Excute this request
         alert(JSON.stringify(resultObj));
         jQuery.ajaxSetup({async: true});
         resetForm();                                        // REset the Form data
        }
    </script>
    
    </body>
    </html>

6.Other information





