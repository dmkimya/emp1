
# customer-product-managment quick start 

## Initialize firebase for localhost


Open **firebaseConfig.js** and paste your firebase config
```bash

export default {
    apiKey: "***************-********",
    authDomain: "public-manager.firebaseapp.com",
    projectId: "public-manager",
    storageBucket: "public-manager.appspot.com",
    messagingSenderId: "***********",
    appId: "1:********:web:*********"
  };

# install dependencies
$ npm install

# serve with hot reload at localhost:3000
$ npm run dev

```
and project will work for localhost without admin.


## Set admin user locally


```bash
# create new folder
$ mkdir setAdmin

# go inside
$ cd setAdmin

# initialize npm
$ npm init

# install firebase-admin
$ npm i firebase-admin

# create app.js

# paste codes and run command
$ node app.js

const admin = require("firebase-admin");

//go firebase and create admin sdk key and paste there
const serviceAccount ={
  "type": "*************",
  "project_id": "***********",
  "private_key_id": "*************",
  "private_key": "*******",
  "client_email": "********",
  "client_id": "************",
  "auth_uri": "***************",
  "token_uri": "****************",
  "auth_provider_x509_cert_url": "*****************",
  "client_x509_cert_url": "**************"
}


admin.initializeApp({
  credential: admin.credential.cert(serviceAccount),
  databaseURL: `https://${serviceAccount.project_id}-default-rtdb.firebaseio.com`,
});

 let uid = "*********"; //admin user id

admin
  .auth()
  .setCustomUserClaims(uid, { admin: true }) //if you want to change user status set admin=false
  .then((data) => {
    console.log(data);
  }); 

```


All customers in this page

![Main-Page](https://user-images.githubusercontent.com/75936754/117592656-1a2c4980-b142-11eb-944c-0e8d0c312109.png)

If you want to shopping a spesific customer .you must use this page

![Spesific-Customer](https://user-images.githubusercontent.com/75936754/117592732-67102000-b142-11eb-86d3-5b5955351414.png)

Pdfs looks like this

![pdfwiev](https://user-images.githubusercontent.com/75936754/117746579-5086c900-b215-11eb-90ba-d34daabb0d52.jpg)


There is a all products list.You can manage products.

![Products](https://user-images.githubusercontent.com/75936754/117592766-8a3acf80-b142-11eb-90cf-4e946829d7e9.png)

Single product count logs

![Products-logs](https://user-images.githubusercontent.com/75936754/121882566-61958f00-cd19-11eb-8a56-9dc2e0d08b85.png)

You can watch your shopping logs with date range

![shopping-logs](https://user-images.githubusercontent.com/75936754/121882410-2abf7900-cd19-11eb-91ba-f255c2ba7200.png)





