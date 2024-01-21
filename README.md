# Simple Restaurant Management System

Simple Restaurant Management System adalah sebuah aplikasi yang dikembangkan menggunakan Java dan Spring Framework. Aplikasi ini dirancang untuk membantu pengelolaan operasional pada restoran dengan cara yang efisien dan mudah digunakan. Aplikasi hanya berupa prototype dan masih banyak kekurangan dan memerlukan fitur tambahan. Beberapa fitur yang ada pada aplikasi ini adalah :

- Signup User
- Admin Menyetujui Status Akun User
- Login User
- Change Password
- Forgot Password
- Simple CRUD untuk table user, category, product dan table
- Membuat bill dalam bentuk PDF


## API Reference

### User
#### Signup

```http
  POST /user/signup
  Body
  {
    "name":,
    "contactNumber" : ,
    "email": ,
    "password" : 
  }
```

#### Login

```http
  POST /api/items
  Body
  {
    "email": ,
    "password" : 
  }
```

#### Change Password

```http
  POST /user/changePassword
  Body
  {
    "oldPassword": ,
    "newPassword":
  }
```

#### Forgot Password

```http
  POST /user/forgotPassword
  Body
  {
    "email": ,
  }
```

### Category
#### Add
```http
  POST /category/add
  Body
  {
    "name":,
  }
```
#### Get
```http
  GET /category/get
```
#### Update
```http
  POST /category/update
  Body
  {
    "name":,
  }
```

### Product
#### Add
POST /product/add
```http
  Body
  {
    "categoryId" : ,
    "name" : ",
    "description" : ,
    "price" : 
  }
```
#### Get
```http
GET /product/get
```
#### Update
```http
  Body
  {
    "categoryId" : ,
    "name" : ",
    "description" : ,
    "price" : ,
    "id"    : 
  }
```
#### Delete
```http
POST /delete/{id}
```
#### UpdateStatus
POST /updateStatus
```http
  Body
  {
    "status" : ,
    "id"    : 
  }
```
#### GetByCategory
```http
GET /product/getByCategory{id}
```
#### GetById
```http
GET /product/getById{id}
```

### Bill
#### GenerateBill
```http
POST /bill/generateBill
  Body
  {
  "filename": ,
  "contactNumber": ,
  "email": ,
  "name": ,
  "paymentMethod": ,
  "productDetails": ,
  "totalAmount": 
  }
```
#### GetBills
```http
GET /bill/GetBills
```

#### GetPDF
```http
POST /bill/generateBill
  Body
  {
  "filename": ,
  "contactNumber": ,
  "email": ,
  "name": ,
  "paymentMethod": ,
  "productDetails":[JSON Array],
  "totalAmount": ,
  "uuid": ,
  }
```
#### Delete
```http
POST /bill/delete/{id}
```

## Appendix

Notes :
- Semua API membutuhkan role admin
- Membuat akun admin terlebih dahulu pada database dengan status true

SQL Command

INSERT INTO user (id, contact_number, email, name, password, role, status)
VALUES
  (1, '123456789', 'admin@example.com', 'Admin User', 'admin_password', 'admin', 'true');

- Agar dapat menerima email pada fitur updateStatusUser oleh admin dan forgot password, pastikan email pada database berupa email aktif atau menggunakan mailinator.com

- Pada CafeConstants pada variable : public static final String STORE_LOCATION = "D:\\Log"; pastikan sesuaikan dengan folder anda.

## Screenshots

### Contoh account approved
[![image.png](https://i.postimg.cc/c1BMmbnm/image.png)](https://postimg.cc/SjjMQVV2)

### Forgot Password
[![image.png](https://i.postimg.cc/RCWJ3pTh/image.png)](https://postimg.cc/G91mVQVn)

### Contoh File PDF
[![image.png](https://i.postimg.cc/T3pVT2H7/image.png)](https://postimg.cc/w1YyVzzL)

### Database User
[![image.png](https://i.postimg.cc/sfWDdkcY/image.png)](https://postimg.cc/6T9NC1Fq)

### Database Category
[![image.png](https://i.postimg.cc/tgmCpyw5/image.png)](https://postimg.cc/2qhfxpzb)

### Database Product
[![image.png](https://i.postimg.cc/Yqc0vr9D/image.png)](https://postimg.cc/4n5sMTpp)

### Database Bill
[![image.png](https://i.postimg.cc/9QLcYCmh/image.png)](https://postimg.cc/DSbV2V4j)

### Contoh Postman getProduct
[![image.png](https://i.postimg.cc/Kjhb8YNn/image.png)](https://postimg.cc/bDgW6p4J)

### Contoh Postman getCategory
[![image.png](https://i.postimg.cc/5tHW5zKB/image.png)](https://postimg.cc/f3hPDVNy)

### Contoh Postman generateBill
[![image.png](https://i.postimg.cc/bNzXCWFN/image.png)](https://postimg.cc/DmYYmjTt)
