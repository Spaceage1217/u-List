# u-List
u-List for the students by the students

## API SPEC
### Users (to authenticate a user)
    {
      "user": {
        "email": "vincent@gmail.com",
       "token": "jwt token or flask token",
        "username": "Vince",
        "bio": "CS Student",
        "image":"some/path"
      }
    }
### Profile of a user

    {
        "profile": {
            "username": "Vince",
            "bio": "CS student",
            "image": "some/path",
            "following": false
        }
    }
### Listing

    {
        "listing": {
             "slug": "cs-1428-book-#123",
             "title": CS 1428 book",
             "description": "1428 text book 5th edition",
             "category": "Books",
             "Department?": "CS",//departments might be optional depending on the category.
             "Price": "100.00",
             "tags": ["cs", "books","programming"],
             "createdAt": "2017-08-5T03:22:56.637Z", //will be time stamps
             "updatedAt": "2017-09-13T03:48:35.824Z",//will be time stamps
             "favorite": false,
             "favoritesCount": 0,
             "owner": {
              "username": "vince",
             "bio": "CS Student",
             "image": "some/path",
             "following": false
             }
         }
    }
### Listings (multiple)
    {
        "listings":[ {
            "slug": "cs-1428-book-#123",
            "title": CS 1428 book",
            "description": "1428 text book 5th edition",
            "category": "Books",
            "Department?": "CS",//departments might be optional depending on the category.
            "Price": "100.00",
            "tags": ["cs", "books","programming"],
            "createdAt": "2017-08-5T03:22:56.637Z", //will be time stamps
            "updatedAt": "2017-09-13T03:48:35.824Z", //will be time stamps
            "favorite": false,
            "favoritesCount": 0,
            "owner": {
                "username": "vince",
                "bio": "CS Student",
                "image": "some/path",
                "following": false`
            }
        }
        ,{
            "slug": "cs-2308-book-#123",
            "title": CS 2308 book",
            "description": "2308 text book 5th edition",
            "category": "Books",
            "Department?": "CS",//departments might be optional depending on the category.
            "Price": "100.00",
            "tags": ["cs", "books","programming"],
            "createdAt": "2017-08-5T03:22:56.637Z", //will be time stamps
            "updatedAt": "2017-09-13T03:48:35.824Z", //will be time stamps
            "favorite": false,
            "favoritesCount": 0,
            "owner": {
                "username": "vince",
                "bio": "CS Student",
                "image": "some/path",
                "following": false`
            }    
         }],
         "listingCount": 2
    }
### Endpoints
_______________________________________
#### login
 A `POST` request to the API/users/login should be made.<br/>
**Returns:** A user.<br/>
**Requires:** `email`, `password`<br/>
**Authentication required:** None.<br/>
###### Example request body:<br/>
    {
        "user":{
            "email": "vince@gmail.com",
            "password": "blah123"
        }
    }

#### registration
A `POST` request to the API/users should be made.<br/>
**Returns**: A user.<br/>
**Requires**: `email`, `username` `password`.<br/>
**Authentication required**: None.<br/>
###### Example request body:<br/>
    {
        "user":{
            "username": "Vicne",`
            "email": "vince@gmail.com",`
            "school-email": "vince@txstate.edu",`
            "password": "blah123"`
        }
    }

#### Get Current User
A `GET` request to the API/user should be made.<br/>
**Authentication required:** check to make sure user is still logged in.<br/>
**Returns:** A User that's the current user.<br/>
#### Update User 
A `PUT` request to the API/user should be made.<br/>
**Authentication required:** Check to make sure user is still logged in.<br/>
**Returns:** The User.<br/>
Accepted fields that can be changed: `email`, `username`, `password`, `image`, `bio`<br/>
###### Example request body:

    {
        "user":{
            "email": "vince@gmail.com",
            "bio": "CS student",
            "image": "some/path"
        }
    }


#### Get Profile
A `GET` request to the API/profiles/:username should be made.<br/>
Returns: A Profile<br/>
**Authentication required:** None.<br/>
### Get Listings
A `GET` request to the API/listings should be made. <br/>
**Returns:** most recent listings globally be default, provide `tag`, `owner`, `favorited`,`department`,`category`, or `price range` query parameter to filter results<br/>
**Authentication required:** None.<br/>
##### Query Parameters:

**Filter by tag:**
`?tag=1428`<br/>
**Filter by owner:**
`?owner=vince`<br/>
**Favorited by user:**
`?favorited=sherm`<br/>
**Limit number of listings** 
`?limit=15`<br/>
**Max-price**
`?maxPrice=150.00`<br/>
>**Note:** (default for listings is 15 per page..still figuring out design might change):
#### Get listing
A `GET` request to the API/listings/:slug should be made.<br/>
**Authentication required**: None.<br/>
**Returns:** Single listing.<br/>

#### Create Listing
A `Post` request to the API/listings should be made.<br/>
**Authentication required**: yes needs to be logged in.<br/>
**Returns:** A listing.<br/>
**Required fields**: `title`, `description`,`price`,`category`,`department //might depend on the category`<br/>
**Optional fields**: `tags` as an array of Strings.<br/>
>**Note:** Might phase out the idea of sorting by department all together might not be usefull in the long run..

##### Example request body:

    {
        "listings": {
            "title": "CS 1428 book",
            "description": "CS 1428 book 5th edition",
            "category": "book",
            "Department?": "CS",//departments might be optional depending on the category.
            "Price": "100.00"
            "tags": ["1428", "CS"]
        }
    }

#### Update Listing
A `PUT` request to the API/listings/:slug should be made.<br/>
**Authentication required**: yes needs to be logged in.<br/>
**Returns:** A updated Listing.<br/>
**Optional fields**: `title`, `description`, `price`,`department`,`category`<br/>

>**Note:** The slug also gets updated when the title is changed

##### Example request body:
    {
        "Listing": {
            "title": "2308 4th edition"
        }
    }

#### Delete Listing
A `DELETE` request to the API/listings/:slug should be made.
**Authentication required**: Yes user needs to be logged in.<br/>





