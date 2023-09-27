Authentication server


Build with:

docker build --tag authi .   
docker run -d -it -p 8000:8000 authi

@baseUrl = http://127.0.0.1:8000
@contentType = application/json


GET {{baseUrl}}/users/ HTTP/1.1

### ----------------- ###

POST {{baseUrl}}/register/ HTTP/1.1
Content-Type: {{contentType}}

{
    "username": "pepe22",
    "first_name": "pepon",
    "last_name": "pentoski",
    "password": "1234"
}

### ----------------- ###

POST {{baseUrl}}/login/ HTTP/1.1
Content-Type: {{contentType}}

{
    "username": "pepe22",
    "password": "1234"
}

### ----------------- ###

GET {{baseUrl}}/me/ HTTP/1.1
Content-Type: {{contentType}}
Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiJqdWFuOTk5IiwiZXhwIjoxNjgzOTk5NjExfQ.Z1jgEvksFd7ZGB4uUxQzdIxRDGfmNf9jFPfeM-TBub0

### ----------------- ###

POST {{baseUrl}}/refresh/ HTTP/1.1
Content-Type: {{contentType}}

{
    "refresh_token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiJqdWFuOTk5IiwiZXhwIjoxNjg0MDM4NDYwfQ.GiEn9Gc4kL3_KkRAbwfIn2tpqn0dDNGGjRu3iGj3VU0"
}

### ----------------- ###

GET {{baseUrl}}/users/ HTTP/1.1



