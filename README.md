# u-List
u-List for the students by the students

# API SPEC
### Users (to authenticate a user)
`{`
&nbsp; &nbsp;  `"user": {`
&nbsp; &nbsp;&nbsp; &nbsp;    `"email": "vincent@gmail.com",`
&nbsp; &nbsp;&nbsp; &nbsp;   ` "token": "jwt token or flask token",`
&nbsp; &nbsp;&nbsp; &nbsp;    `"username": "Vince",`
&nbsp; &nbsp;&nbsp; &nbsp;    `"bio": "CS Student",`
&nbsp; &nbsp; &nbsp; &nbsp;   `"image":"some/path"`
&nbsp; &nbsp;  `}`
`}`
### Profile of a user

`{`
&nbsp; &nbsp; ` "profile": {`
&nbsp; &nbsp;&nbsp; &nbsp;   `"username": "Vince",`
&nbsp; &nbsp;&nbsp; &nbsp;    `"bio": "CS student",`
&nbsp; &nbsp; &nbsp; &nbsp;   `"image": "some/path",`
&nbsp; &nbsp; &nbsp; &nbsp;   `"following": false`
&nbsp; &nbsp;  `}`
`}`
### Listing

`{`
&nbsp; &nbsp; ` "listing": {`
&nbsp; &nbsp;&nbsp; &nbsp;   ` "slug": "cs-1428-book-#123",`
&nbsp; &nbsp;&nbsp; &nbsp;    `"title": CS 1428 book",`
&nbsp; &nbsp;&nbsp; &nbsp;  `  "description": "1428 text book 5th edition",`
&nbsp; &nbsp;&nbsp; &nbsp;  `  "category": "Books",`
&nbsp; &nbsp;&nbsp; &nbsp;  `  "Department?": "CS",//departments might be optional depending on the category.`
&nbsp; &nbsp;&nbsp; &nbsp;  `  "Price": "100.00",`
&nbsp; &nbsp;&nbsp; &nbsp;   ` "tags": ["cs", "books","programming"],`
&nbsp; &nbsp;&nbsp; &nbsp;   ` "createdAt": "2017-08-5T03:22:56.637Z", //will be time stamps`
&nbsp; &nbsp;&nbsp; &nbsp;  `  "updatedAt": "2017-09-13T03:48:35.824Z",//will be time stamps`
&nbsp; &nbsp;&nbsp; &nbsp;    `"favorite": false,`
&nbsp; &nbsp;&nbsp; &nbsp;   ` "favoritesCount": 0,`
&nbsp; &nbsp;&nbsp; &nbsp;   ` "owner": {`
&nbsp; &nbsp;&nbsp; &nbsp;&nbsp; &nbsp;    `  "username": "vince",`
&nbsp; &nbsp;&nbsp; &nbsp;&nbsp; &nbsp;     ` "bio": "CS Student",`
&nbsp; &nbsp;&nbsp; &nbsp;&nbsp; &nbsp;     ` "image": "some/path",`
&nbsp; &nbsp;&nbsp; &nbsp;&nbsp; &nbsp;    `  "following": false`
&nbsp; &nbsp;&nbsp; &nbsp;   ` }`
 `}`
`}`
### Listings (multiple)
`{`
&nbsp; &nbsp;`  "listings":[ {`
  &nbsp; &nbsp; &nbsp; &nbsp;` "slug": "cs-1428-book-#123",`
  &nbsp; &nbsp;  &nbsp; &nbsp; `"title": CS 1428 book",`
  &nbsp; &nbsp; &nbsp; &nbsp;` "description": "1428 text book 5th edition",`
  &nbsp; &nbsp; &nbsp; &nbsp;`  "category": "Books",`
  &nbsp; &nbsp;&nbsp; &nbsp;  `  "Department?": "CS",//departments might be optional depending on the category.`
  &nbsp; &nbsp;&nbsp; &nbsp;  `  "Price": "100.00",`
  &nbsp; &nbsp; &nbsp; &nbsp; ` "tags": ["cs", "books","programming"],`
  &nbsp; &nbsp; &nbsp; &nbsp; ` "createdAt": "2017-08-5T03:22:56.637Z", //will be time stamps`
  &nbsp; &nbsp; &nbsp; &nbsp;`  "updatedAt": "2017-09-13T03:48:35.824Z", //will be time stamps`
  &nbsp; &nbsp; &nbsp; &nbsp; `"favorite": false,`
 &nbsp; &nbsp; &nbsp; &nbsp; ` "favoritesCount": 0,`
 &nbsp; &nbsp; &nbsp; &nbsp; ` "owner": {`
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;  `  "username": "vince",`
&nbsp; &nbsp;  &nbsp; &nbsp; &nbsp; &nbsp;  ` "bio": "CS Student",`
&nbsp; &nbsp;  &nbsp; &nbsp; &nbsp; &nbsp;  ` "image": "some/path",`
&nbsp; &nbsp;  &nbsp; &nbsp; &nbsp; &nbsp; `  "following": false`
&nbsp; &nbsp; &nbsp; &nbsp;  ` }`
 `}`
  `, {`
&nbsp; &nbsp;  &nbsp; &nbsp; ` "slug": "cs-2308-book-#123",`
&nbsp; &nbsp; &nbsp; &nbsp;   `"title": CS 2308 book",`
&nbsp; &nbsp; &nbsp; &nbsp; `  "description": "2308 text book 3red edition",`
&nbsp; &nbsp;  &nbsp; &nbsp;`  "category": "Books",`
&nbsp; &nbsp;&nbsp; &nbsp;  `  "Department?": "CS",//departments might be optional depending on the category.`
&nbsp; &nbsp;&nbsp; &nbsp;  `  "Price": "100.00",`
&nbsp; &nbsp;  &nbsp; &nbsp; ` "tags": ["cs", "books","programming"],`
&nbsp; &nbsp;  &nbsp; &nbsp; ` "createdAt": "2017-08-5T03:22:56.637Z", //will be time stamps`
&nbsp; &nbsp;  &nbsp; &nbsp;`  "updatedAt": "2017-09-13T03:48:35.824Z", //will be time stamps`
&nbsp; &nbsp;  &nbsp; &nbsp;  `"favorite": false,`
&nbsp; &nbsp;  &nbsp; &nbsp; ` "favoritesCount": 0,`
&nbsp; &nbsp;  &nbsp; &nbsp; ` "owner": {`
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;  `  "username": "vince",`
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;   ` "bio": "CS Student",`
&nbsp; &nbsp;  &nbsp; &nbsp; &nbsp; &nbsp;  ` "image": "some/path",`
&nbsp; &nbsp;  &nbsp; &nbsp; &nbsp; &nbsp; `  "following": false`
&nbsp; &nbsp;  &nbsp; &nbsp; ` }`
 &nbsp; &nbsp;`}],`
  &nbsp; &nbsp;`"listingCount": 2`
`}`
### Endpoints
_______________________________________
#### login
 A `POST` request to the API/users/login should be made.
**Returns:** A user.
**Requires:** `email`, `password`
**Authentication required:** None.
`{`
 &nbsp; &nbsp;`  "user":{`
 &nbsp; &nbsp; &nbsp; &nbsp; `   "email": "vince@gmail.com",`
 &nbsp; &nbsp; &nbsp; &nbsp;  `  "password": "blah123"`
 &nbsp; &nbsp; ` }`
`}`

#### registration
A `POST` request to the API/users should be made.
**Returns**: A user.
**Requires**: `email`, `username` `password`.
**Authentication required**: None.
`{`
 &nbsp; &nbsp; `  "user":{`
 &nbsp; &nbsp;  &nbsp; &nbsp; `    "username": "Vicne",`
 &nbsp; &nbsp;  &nbsp; &nbsp; `    "email": "vince@gmail.com",`
 &nbsp; &nbsp;  &nbsp; &nbsp; `    "school-email": "vince@txstate.edu",`
 &nbsp; &nbsp;  &nbsp; &nbsp; `    "password": "blah123"`
 &nbsp; &nbsp; `  }`
`}`

#### Get Current User
A `GET` request to the API/user should be made.
**Authentication required:** check to make sure user is still logged in.
**Returns:** A User that's the current user.
#### Update User 
A `PUT` request to the API/user should be made.
**Authentication required:** Check to make sure user is still logged in.
**Returns:** The User
Accepted fields that can be changed: `email`, `username`, `password`, `image`, `bio`
Example request body:
`{`
 &nbsp; &nbsp; `  "user":{`
 &nbsp; &nbsp;  &nbsp; &nbsp;  `   "email": "vince@gmail.com",`
 &nbsp; &nbsp;  &nbsp; &nbsp;  `   "bio": "CS student",`
 &nbsp; &nbsp;  &nbsp; &nbsp;  `   "image": "some/path"`
 &nbsp; &nbsp; `  }`
`}`


#### Get Profile
A `GET` request to the API/profiles/:username should be made.
Returns: A Profile
**Authentication required:none**
### Get Listings
A `GET` request to the API/listings should be made. 
**Returns:** most recent listings globally be default, provide `tag`, `owner`, `favorited`,`department`,`category`, or `price range` query parameter to filter results
**Authentication required**: None
##### Query Parameters:

**Filter by tag:**
`?tag=1428`
**Filter by owner:**
`?owner=vince`
**Favorited by user:**
`?favorited=sherm`
**Limit number of listings** 
`?limit=15`
**Max-price**
`?maxPrice=150.00`
>**Note:** (default for listings is 15 per page..still figuring out design might change):
#### Get listing
A `GET` request to the API/listings/:slug should be made.
**Authentication required**: None.
**Returns:** Single listing.

#### Create Listing
A `Post` request to the API/listings should be made.
**Authentication required**: yes needs to be logged in.
**Returns:** A listing.
**Required fields**: `title`, `description`,`price`,`category`,`department //might depend on the category`
**Optional fields**: `tags` as an array of Strings
>**Note:** Might phase out the idea of sorting by department all together might not be usefull in the long run..

##### Example request body:

`{`
 &nbsp; &nbsp; `  "listings": {`
 &nbsp; &nbsp; &nbsp; &nbsp; `    "title": "CS 1428 book",`
 &nbsp; &nbsp;  &nbsp; &nbsp; `    "description": "CS 1428 book 5th edition",`
 &nbsp; &nbsp;  &nbsp; &nbsp; `  "category": "book",`
 &nbsp; &nbsp;&nbsp; &nbsp;  `  "Department?": "CS",//departments might be optional depending on the category.`
 &nbsp; &nbsp;&nbsp; &nbsp;  `  "Price": "100.00",`
 &nbsp; &nbsp;  &nbsp; &nbsp; `    "tags": ["1428", "CS"]`
 &nbsp; &nbsp; `  }`
`}`

#### Update Listing
A `PUT` request to the API/listings/:slug should be made.
**Authentication required**: yes needs to be logged in.
**Returns:** A updated Listing.
**Optional fields**: `title`, `description`, `price`,`department`,`category`

>**Note:** The slug also gets updated when the title is changed

##### Example request body:
`{`
 &nbsp; &nbsp; ` "Listing": {`
 &nbsp; &nbsp;  &nbsp; &nbsp; `"title": "2308 4th edition"`
 &nbsp; &nbsp; `  }`
`}`

#### Delete Listing
A `DELETE` request to the API/listings/:slug should be made.
**Authentication required**: yes needs to be logged in.




