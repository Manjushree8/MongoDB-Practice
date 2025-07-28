# MongoDB-Practice

This repository contains my hands-on practice using **MongoDB** via the **mongosh shell**. The goal was to understand basic database operations including inserting, updating, querying, and deleting documents in a collection.

---

## 📂 Project Overview

**Database Name:** `libraryDB`  
**Collection Used:** `books`

---

## 🔧 Commands Practiced

### ✅ Creating and Switching Database
```js
use libraryDB
```

### ✅ Creating Collection
```js
db.createCollection("books")
```

### ✅ Inserting Documents

```js
// Single document
db.books.insertOne({
  title: "Me Before You",
  author: "Jojo Moyes",
  genre: "Romantic Drama",
  year: 2012,
  available: true,
  copies: 5
})

// Multiple documents
db.books.insertMany([
  {
    title: "The Flatshare",
    author: "Beth O'Leary",
    genre: "Romantic Comedy",
    year: 2019,
    available: true,
    copies: 3
  },
  {
    title: "The Spanish Love Deception",
    author: "Elena Armas",
    genre: "Romantic Comedy",
    year: 2021,
    available: true,
    copies: 2
  }
])
```

### ✅ Querying Documents

```js
db.books.find()
db.books.find({ genre: "Romantic Comedy" })
db.books.find({ copies: { $lt: 4 } })
db.books.find({ vibe: { $regex: "Emotional", $options: "i" } })
```

### ✅ Updating Documents

```js
db.books.updateOne(
  { title: "The Spanish Love Deception" },
  { $set: { copies: 3 } }
)

db.books.updateMany(
  { genre: "Romantic Comedy" },
  { $set: { recommended: true } }
)
```

### ✅ Deleting Documents

```js
db.books.deleteOne({ title: "It Ends With Us" })
db.books.deleteMany({})
```

### ✅ Other Operators

```js
db.books.find({
  $and: [{ available: true }, { copies: { $gt: 3 } }]
})

db.books.find({
  $or: [{ genre: "Romantic Drama" }, { year: { $lt: 2016 } }]
})

db.books.find({
  publisher: { $exists: false }
})

db.books.find({
  genre: { $in: ["Romantic Drama", "Romantic Comedy"] }
})
```

---

## 🧠 Learnings

- Practiced **insert**, **find**, **update**, **delete** operations.
- Learned use of operators like `$and`, `$or`, `$in`, `$exists`, `$regex`.
- Applied MongoDB in a practical context with a **library management system**.

---

## 📸 Screenshots

![Screenshot 1](Screenshots/Screenshot%202025-07-28%20110010.png)


![Screenshot 2](Screenshots/Screenshot%202025-07-28%20110144.png)


![Screenshot 3](Screenshots/Screenshot%202025-07-28%20110214.png)


![Screenshot 4](Screenshots/Screenshot%202025-07-28%20110246.png)


![Screenshot 5](Screenshots/Screenshot%202025-07-28%20110307.png)


![Screenshot 6](Screenshots/Screenshot%202025-07-28%20110330.png)

---

## 📌 Technologies Used

- MongoDB 8.0.12  
- Mongosh Shell 2.5.6  
- Git & GitHub

---

## ✍️ Author

**Manjushree Venkatesan**  
💻 Full Stack Web Developer  
🌐 GitHub: [@Manjushree8](https://github.com/Manjushree8)
