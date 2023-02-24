# *Interviews Of Employes Inquiry Data*

This project is a inquires of employes **who had attend to interview** in a company.

This **inquiry** application allows users to **Create** , **Read** , **Update** , **Delete** their employs details.

## *MongoDB Schema(db)*

### *Inquiry Collection*
***
- _id : `INT` (it will automatically generate by MongoDB)
- Name            : `String`
- Age             :  `Number`
- Marriage Status : `string`
- Skills          : `String`
- Education       : `String`
- Experience      : `string`

## *Steps*
1. First we have create a database **(interview)** in mongodb .
2. Create Collection (**inquiry**)in DB **(interview)** which we had created.
3. Now , we have to open **mangoosh** shell 
in mongodb.


### *Comands*

**Changing to DB **(interview)** which we have created.**

```
test > use interview
```
Terminal changes into ,

```
interview >
```

## *Applying CRUD operations*

### *CRUD*

- Create : `.insertOne` (or) `.insertMany`
- Read  : `.find()` (or) `.find({})`
- Update : `.updateOne` (or) `.updateMany`
- Delete : `.deleteMany({})`(or)`.delete       ({selection statement})`


## *1. Create*

Inserting a **single** document in collection (inquiry).
```js
db.inquiry.insertOne({"name":"Muneer Basha",
"age":38,
"marriage status": "Yes",
"email":"muneer@gmail.com",
"phonenumber":"7780301577",
"skills":[ "Json" , "Sql" , "Python"],
"experience":"Yes"})
```
**Syntax :**

```
db.collection name.insertOne({})
```
***
Inserting a **multi** document in collection (inquiry).
***

```js

db.inquiry.insertMany([{"name":"Meeravali",
"age":32,
"marriage status": "Yes",
"email":"Meera@gmail.com",
"phonenumber":"9700787228",
"skills":[  "Sql" , "Python", "Java sript"],
"experience":"No"},

{"name":"Muskan Fathima",
"age":20,
"marriage status": "No",
"email":"muskan@gmail.com",
"phonenumber":"9570301426",
"skills":[ "Json" , "Sql" ],
"experience":"Yes"},

{"name":"Jareena",
"age":29,
"marriage status": "Yes",
"email":"Jarru@gmail.com",
"phonenumber":"8555835021",
"skills":[ "Json" , "Sql" , "Python", "HTML"],
"experience":"No"}]
)

```
**Syntax**

```js
db.collection name.insertMany([{},{},{} .... ])
```
***
## *2. Read*
***

Finding all documents in collection (inquiry)

```js
db.inquiry.find()
```

Finding a particular document by its `_id`.

```js
db.inquiry.find({_id:Object("63f85f57ca60226bc3fd14ec")})
```

Finding a particular document by its `email`.


```js
db.inquiry.find({"email":"muneer@gmail.com"})
```

This way we can find any document by changing **selection statement** in object.
***
## *Update*
***
Updating the **marriage status**,**age** of the **single** document.

```js
db.inquiry.updateOne({"email":"Jarru@gmail.com"},{$set:{"marriage status":"no","age":"28"}})
```
Updating the **marriage status** of **all** documents.

```js
db.inquiry.updateMany({"age":18},{$set{"marriage status":"no"}})
```

## *Delete*

Deleting **all** documents in the collection.

```js
db.inquiry.deleteMany({})
```

Deleting **single** document in the collection by its name.

```js
db.inquiry.deleteOne({"name":"Jareena"})
```

This way we can delete any documents by changing selected statement in the object.

## *Nested object and array*
InsertOne
```js
db.inquiry.insertOne({
     "name":"MuneerBasha",
     "skills":
     [{"name":"python","rating":5},
       {"name":"sql","rating":7},
     {"name":"Jshon","rating":9}],
     "education":
     [{"institute":"Government girls high school","type":"ssc","year":"1986-1990"},
     {"institute":"Sri chaithanya","type":"Intermideate","year":"1990-1993"},
     {"institute":"KITS","type":"BTEC","year":"1993-1998"}],
     "Married":"Yes",
     "children":3,"age":38})
```
InserMany
```

db.inquiry.insertMany([{
     "name":"Muskan",
     "skills":
     [{"name":"python","rating":6},
     {"name":"sql","rating":7},
     {"name":"Jshon","rating":9}],
     "education":
     [{"institute":"Vaasavi high school","type":"ssc","year":"2016-2022"},
     {"institute":"Sri chaithanya","type":"Intermideate","year":"2022-2024"},
     {"institute":"KITS","type":"BTEC","year":"2024-2029"}],
     "Married":"No",
     "children":"NO",
     "age":21},
     
     {"name":"Jarru",
     "skills":
     [{"name":"python","rating":6},
     {"name":"sql","rating":7},
     {"name":"Json","rating":9}],
     "education":
     [{"institute":"ZPhigh school","type":"SSC","year":"1990-2000"},
     {"institute":"Womens college","type":"Intermideate","year":"2000-2013"}],
     "married":"yes",
     "childern":2,"age":30}])
```

>In Json we call **Square brackets** as **Array** , **Curly Brace** as **Object**.

    




