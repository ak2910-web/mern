## Practical No. 8

## Practical 8C - Test REST APIs Using Postman.

**Aim:** - Aim: API Creation and Integration

### c) Test REST APIs Using Postman.

Procedure

Install Postman

1 Open your web browser and visit:

postman.com

https://www.postman.com/downloads/

2 Download the Windows 64-bit version.

3 Run the downloaded installer.

4 Follow the installation wizard and click Install.

5 After installation open Postman.

Skip Login (Recommended for Students)

When Postman opens, it may ask you to sign in.

Choose one of these options:

Skip and go to the app

Continue without an account (Depending on the version, the wording may differ.)

Create Your First Request

Click New or the + tab.

Select HTTP Request.

At the top, change the request method to GET.

Enter the URL:

localhost:3000

Click Send.

If your Express server is running, you will see the response from your API.

Test POST Request

Change the method to POST.

Enter the URL: localhost:3000/students

Click Body.

Select raw.

From the dropdown, choose JSON

Enter:

```js
{
```

"name": "Rahul Sharma",

"course": "B.Sc. Information Technology",

"semester": 5,

"city": "Mumbai"

```js
}
```

Click Send.

If successful, the inserted document will be displayed in the response.

Open Postman and test the following requests

Method Url GET http://localhost:3000/students PUT http://localhost:3000/students/:id DELETE http://localhost:3000/students/:id

**Output**

Perform the following operations in Postman:

Insert a student record.

Retrieve all student records.

Update a student record.

Delete a student record
