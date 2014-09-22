FORMAT: 1A

# E-Library API

# Group Authentication

## POST /oauth2/token 

Request for an access token using the Oauth2 User Password/Credentials flow.

+ Request
  
    + Headers

            Content-Type: application/x-www-form-urlencoded

    + Body

            grant_type=password
            client_id=testclient
            client_secret=testsecret
            user_unique_id=2009/1/32435CT
            user_password=123456

+ Response 200 (application/json)

            {
              "data":{
                "access_token":"3d87aae50a5aa0e504af1bc10f658c29e14ddb87260aa8ee395f1270d68f1679b9d78d5b23a5472bacd1abc9b03b21ce",
                "token_type":"Bearer",
                "expires_in":3600,
                "created_at":"2014-09-22T01:02:20.017Z",
                "user_id":1
              }
            }

# Group Books

## GET /books/

Gets book collection. A more specific collection may be retrieved using filters as described below.

Additionally, you can use the `filter` query to get a specific collection. Supported filters

- GET /books?filter=10_most_borrowed
- GET /books?filter=10_latest

** Note ** You can change the value of '10' to any number

+ Request

    + Headers 

            Authorization: Bearer access_token

+ Response 200 (application/json)

  + Body
            {
              "data": [{
                "id": 1,
                "title": "Asperiores aut",
                "category_id": 4,
                "author": "Dr. Robert Lockman",
                "edition": "4",
                "overview": "Natus aliquam voluptatem voluptatibus illo nemo voluptatum dolorem pariatur. Sequi facilis quae occaecati. Iste laboriosam voluptatem assumenda eos sit id. Neque praesentium molestiae at aut maiores.",
                "preview_image": null,
                "has_soft_copy": 1,
                "has_hard_copy": 1,
                "hard_copies_count": 5,
                "borrow_count": 6,
                "published_at": "1981-04-01T07:00:00.000Z",
                "created_at": "2014-09-15T17:05:15.000Z",
                "updated_at": "2014-09-15T17:05:15.000Z",
                "category": {
                  "id": 4,
                  "title": "Python",
                  "created_at": "2014-09-15T17:05:15.000Z"
                }
              }, {
                "id": 2,
                "title": "Dolore dolorem repellendus",
                "category_id": 3,
                "author": "Mrs. Eloisa Considine",
                "edition": "4",
                "overview": "Dolorem hic repellat consequatur qui molestiae beatae nulla non. Aut in tempore voluptatum veniam. Necessitatibus veniam velit tenetur. Repellendus aperiam aut sit. Dolorum qui id quisquam facere.",
                "preview_image": null,
                "has_soft_copy": 0,
                "has_hard_copy": 1,
                "hard_copies_count": 8,
                "borrow_count": 0,
                "published_at": "1999-09-01T07:00:00.000Z",
                "created_at": "2014-09-15T17:05:15.000Z",
                "updated_at": "2014-09-15T17:05:15.000Z",
                "category": {
                  "id": 3,
                  "title": "Operating System",
                  "created_at": "2014-09-15T17:05:15.000Z"
                }
              }]
            }

## GET /books/:id/

Gets a specific book resource using the specified id

+ Request

    + Headers 

            Authorization: Bearer access_token

+ Response 200 (application/json)

            {
              "data": {
                "id": 2,
                "title": "Dolore dolorem repellendus",
                "category_id": 3,
                "author": "Mrs. Eloisa Considine",
                "edition": "4",
                "overview": "Dolorem hic repellat consequatur qui molestiae beatae nulla non. Aut in tempore voluptatum veniam. Necessitatibus veniam velit tenetur. Repellendus aperiam aut sit. Dolorum qui id quisquam facere.",
                "preview_image": null,
                "has_soft_copy": 0,
                "has_hard_copy": 1,
                "hard_copies_count": 8,
                "borrow_count": 0,
                "published_at": "1999-09-01T07:00:00.000Z",
                "created_at": "2014-09-15T17:05:15.000Z",
                "updated_at": "2014-09-15T17:05:15.000Z",
                "category": {
                  "id": 3,
                  "title": "Operating System",
                  "created_at": "2014-09-15T17:05:15.000Z"
                }
              }
            }

## GET /books/random

Gets a random book

+ Request 

      + Headers

            Authorization: Bearer access_token
            Content-Type: application/json

+ Response 200 (application/json)

            {
              "data": {
                "id": 2,
                "title": "Dolore dolorem repellendus",
                "category_id": 3,
                "author": "Mrs. Eloisa Considine",
                "edition": "4",
                "overview": "Dolorem hic repellat consequatur qui molestiae beatae nulla non. Aut in tempore voluptatum veniam. Necessitatibus veniam velit tenetur. Repellendus aperiam aut sit. Dolorum qui id quisquam facere.",
                "preview_image": null,
                "has_soft_copy": 0,
                "has_hard_copy": 1,
                "hard_copies_count": 8,
                "borrow_count": 0,
                "published_at": "1999-09-01T07:00:00.000Z",
                "created_at": "2014-09-15T17:05:15.000Z",
                "updated_at": "2014-09-15T17:05:15.000Z",
                "category": {
                  "id": 3,
                  "title": "Operating System",
                  "created_at": "2014-09-15T17:05:15.000Z"
                }
              }
            }

## DELETE /books/:id

Deletes a book. ** Note ** This doesn't remove the book from the library physically. (^_^ )

+ Request 

      + Headers

            Authorization: Bearer access_token
            Content-Type: application/json

+ Response 200 (application/json)

            {
              "data": {
                "id": 544
              }
            }

## POST /books/:id

Updates a book. 

Updatable parameters: title, copies,

+ Request 

    + Headers

            Authorization: Bearer access_token
            Content-Type: application/json

    + Body

            {
              "title": "Some title",
              "copies": 10
            }

+ Response 200 (application/json)

            {
              "data": {
                "id": 544
              }
            }


# Group Print Jobs

# Group Articles

# Group Users

## GET /users/:id

Gets a user data

+ Request

    + Headers 

            Authorization: Bearer access_token

+ Response 200 (application/json)

            {
              "data": {
                "id": 3,
                "registration_id": "2424KJHJ323",
                "unique_id": "212a55cf2e09",
                "email": null,
                "address": "9198 Belle Station Suite 903\nSouth Nellaview, CA 07713-4581",
                "gender": "M",
                "first_name": "Dominique",
                "last_name": "Kulas",
                "type": "staff",
                "created_at": "2014-09-15T17:05:14.000Z",
                "updated_at": "2014-09-15T17:05:14.000Z"
              }
            }

# Group Undocumented API Endpoints

- ** POST ** /users/:id/print-jobs

- ** GET ** /users/:id/print-jobs

- ** GET ** /users/:id/print-jobs/:id

- ** POST ** /users/:id/print-jobs/:id/documents Upload

- ** GET ** /users/:id/print-jobs/:id/documents