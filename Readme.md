Here’s a clean **`README.md`** for your mini project 👇

````markdown
---
# 🍕 Mini Project: Express Application for CRUD Operations on Pizza Store Items

## 📌 Objective
Build a simple Express.js application to perform **CRUD (Create, Read, Update, Delete)** operations on items in a pizza store.  
The application will be tested using **Postman**.

---

## 🛠️ Instructions

### 1. Setup Project Environment
- Create a new folder for the project:
  ```bash
  mkdir pizza-store-crud
  cd pizza-store-crud
````

* Initialize a new Node.js project:

  ```bash
  npm init -y
  ```

### 2. Install Required Packages

Install **Express** (for building the server) and **Nodemon** (for auto-restart during development):

```bash
npm install express
npm install --save-dev nodemon
```

Update `package.json` to add a start script:

```json
"scripts": {
  "start": "node index.js",
  "dev": "nodemon index.js"
}
```

### 3. Create Express Server

* Create `index.js` and set up the server:

  ```js
  const express = require('express');
  const app = express();
  const PORT = 5000;

  // Import routes
  const itemsRoute = require('./routes/items');
  app.use('/items', itemsRoute);

  app.listen(PORT, () => {
      console.log(`Server running on http://localhost:${PORT}`);
  });
  ```

### 4. Define Routes for CRUD Operations

Inside `routes/items.js`, implement routes:

* **GET /items** → Get all pizzas

![alt text](<pictures/Screenshot 2025-09-18 190954.png>)

* **GET /items/\:id** → Get pizza by ID

![alt text](<pictures/Screenshot 2025-09-18 191006.png>)

* **POST /items** → Add new pizza

![alt text](<pictures/Screenshot 2025-09-18 191258.png>)
![alt text](<pictures/Screenshot 2025-09-18 192034.png>)

* **PUT /items/\:id** → Update pizza details

![alt text](<pictures/Screenshot 2025-09-18 192201.png>)
![alt text](<pictures/Screenshot 2025-09-18 192216.png>)

* **DELETE /items/\:id** → Delete pizza by ID

![alt text](<pictures/Screenshot 2025-09-18 192058.png>)
![alt text](<pictures/Screenshot 2025-09-18 192110.png>)

*(You already created GET & DELETE routes. Add POST and PUT if needed.)*

### 5. Test Application Using Postman

1. Run the server:

   ```bash
   npm run dev
   ```
2. Open **Postman** and test:

   * `GET http://localhost:5000/items` → List all pizzas
   * `GET http://localhost:5000/items/1` → Get pizza with ID = 1
   * `POST http://localhost:5000/items` → Add a new pizza (send JSON in Body)
   * `PUT http://localhost:5000/items/2` → Update pizza with ID = 2
   * `DELETE http://localhost:5000/items/3` → Delete pizza with ID = 3

---

## 📂 Project Structure

```
pizza-store-crud/
│── index.js
│── package.json
│── routes/
│   └── items.js
```

---

## 🚀 Sample Pizza Data

```json
[
  {
    "id": 1,
    "name": "Margherita",
    "description": "Classic pizza with tomato sauce, mozzarella, and basil",
    "price": 12.99,
    "category": "Vegetarian",
    "ingredients": ["tomato sauce", "mozzarella", "basil"],
    "available": true
  }
]
```

---

## ✅ Summary

* Built an **Express.js CRUD API** for a Pizza Store.
* Tested endpoints using **Postman**.
* Learned how to handle **routes, params, and CRUD logic** in Express.

