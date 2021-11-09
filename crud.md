## CRUD

1. In your own words, describe what each group of status code represents
   - 100's = provide information to client that header been received and request might fail.
   - 200's = indicate the request was successfully met validations.
   - 300's = requested resources no longer exist.
   - 400's = client request includes some error in it.
   - 500's = for some reason the server can't serve the client

2. What is a status code 202?
   - signals creation of resource.
3. What is a status code 308?
   - permanent url redirection
4. What code would you use if an update didn’t return data to a client?
   - 204
5. What code would you use if a resource used to exist but no longer does?
   - 410
6. What is the ‘Forbidden’ status code?
   - client not authorized to access resources.

## Rest API

1. Why do we need to pull our MongoDB database string out of our server and put it into our .env?
   - to use outside our application when deploy.
2. What is middleware?
   - Function that runs when a server gets a request before it passed to a route
3. What does app.use(express.json()) do?
   - lets the server accept JSON as a body instead of a post/get element
4. What does the /:id mean in a route?
   - it means a parameter
5. What is the difference between PUT and PATCH?
   - Patch updates only the parts the user passes while put updates all the information
6. How do you make a default value in a schema?
   - we use default: someValue;
7. What does a 500 error status code mean?
   - and error on the server side
8. What is the difference between a status 200 and a status 201?
   - 201 successfully created an object while 200 means everything was successful.

## Things I want to know more about
 - More about the different status codes
 - Rest Api
  
#### References:

[Which HTTP Status Code to Use for Every CRUD App](https://www.moesif.com/blog/technical/api-design/Which-HTTP-Status-Code-To-Use-For-Every-CRUD-App/)

[Build A REST API With Node.js, Express, & MongoDB - Quick](https://www.youtube.com/channel/UCFbNIlppjAuEX4znoulh0Cw)



[go to home](README.md)