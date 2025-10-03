## Easy Questions (1–10)

---

### 1️⃣ Retrieve all documents in the collection.  
**Hint:** Use `find()` with no filter to get everything.

**Solution:**
```javascript
db.businesses.find({})
```

---

### 2️⃣ Retrieve the `business_name` of all businesses.  
**Hint:** Use projection to include only the `business_name` field.

**Solution:**
```javascript
db.businesses.find({}, { business_name: 1, _id: 0 })
```

---

### 3️⃣ Retrieve the `business_name` and `certificate_number` of all businesses.  
**Hint:** Use projection to include both fields.

**Solution:**
```javascript
db.businesses.find({}, { business_name: 1, certificate_number: 1, _id: 0 })
```

---

### 4️⃣ Find all businesses where the `result` is **"Violation Issued"**.  
**Hint:** Filter documents using a simple equality match.

**Solution:**
```javascript
db.businesses.find({ result: "Violation Issued" })
```

---

### 5️⃣ Find all businesses where the `result` is **"No Violation Issued"**.  
**Hint:** Similar to the previous, just change the value.

**Solution:**
```javascript
db.businesses.find({ result: "No Violation Issued" })
```

---

### 6️⃣ List all unique values in the `sector` field.  
**Hint:** Use `distinct` to find unique values in a field.

**Solution:**
```javascript
db.businesses.distinct("sector")
```

---

### 7️⃣ Retrieve all documents where `address.city` is **"QUEENS VLG"**.  
**Hint:** Use dot notation to query nested fields.

**Solution:**
```javascript
db.businesses.find({ "address.city": "QUEENS VLG" })
```

---

### 8️⃣ Retrieve all documents where `address.zip` is **11428**.  
**Hint:** Use dot notation again.

**Solution:**
```javascript
db.businesses.find({ "address.zip": 11428 })
```

---

### 9️⃣ Retrieve all documents where the `sector` is **"Cigarette Retail Dealer - 127"**.  
**Hint:** Simple field-value match.

**Solution:**
```javascript
db.businesses.find({ sector: "Cigarette Retail Dealer - 127" })
```

---

### 🔟 Find the business with the `certificate_number` **5381180**.  
**Hint:** Match on `certificate_number` field with exact value.

**Solution:**
```javascript
db.businesses.find({ certificate_number: 5381180 })
```

### 1️⃣1️⃣ Retrieve the `id` and `date` for all businesses.  
**Hint:** Use projection to include only `id` and `date`, and exclude `_id`.

**Solution:**
```javascript
db.businesses.find({}, { id: 1, date: 1, _id: 0 })
```

---

### 1️⃣2️⃣ Find all documents where the `certificate_number` is exactly **9278806**.  
**Hint:** Use an equality match on `certificate_number`.

**Solution:**
```javascript
db.businesses.find({ certificate_number: 9278806 })
```

---

### 1️⃣3️⃣ List all businesses whose `address.city` is **"NEW YORK"**.  
**Hint:** Use dot notation to match nested `city` value.

**Solution:**
```javascript
db.businesses.find({ "address.city": "NEW YORK" })
```

---

### 1️⃣4️⃣ Find all documents where the `address.street` is **"214TH ST"**.  
**Hint:** Match using dot notation on the `address.street` field.

**Solution:**
```javascript
db.businesses.find({ "address.street": "214TH ST" })
```

---

### 1️⃣5️⃣ Retrieve the `business_name` and `sector` of all businesses inspected after **"Feb 15 2015"**.  
**Hint:** Use `$gt` with ISODate for date comparison and projection.

**Solution:**
```javascript
db.businesses.find(
  { date: { $gt: new Date("2015-02-15") } },
  { business_name: 1, sector: 1, _id: 0 }
)
```

---

### 1️⃣6️⃣ Find documents where the `business_name` starts with the letter **"A"**.  
**Hint:** Use a regex pattern anchored at the start of the string.

**Solution:**
```javascript
db.businesses.find({ business_name: /^A/ })
```

---

### 1️⃣7️⃣ List all documents where the `result` is either **"Violation Issued"** or **"No Violation Issued"**.  
**Hint:** Use `$in` to match multiple possible values.

**Solution:**
```javascript
db.businesses.find({ result: { $in: ["Violation Issued", "No Violation Issued"] } })
```

---

### 1️⃣8️⃣ Count the total number of businesses in the collection.  
**Hint:** Use `countDocuments()` to count all documents.

**Solution:**
```javascript
db.businesses.countDocuments()
```

---

### 1️⃣9️⃣ Retrieve businesses whose `address.zip` code is between **10000** and **12000**.  
**Hint:** Use `$gte` and `$lte` with dot notation for range filtering.

**Solution:**
```javascript
db.businesses.find({ "address.zip": { $gte: 10000, $lte: 12000 } })
```

---

### 2️⃣0️⃣ Find documents where the `address.number` is greater than **9000**.  
**Hint:** Use `$gt` with dot notation for comparison.

**Solution:**
```javascript
db.businesses.find({ "address.number": { $gt: 9000 } })
```

---

### 2️⃣1️⃣ Retrieve all documents where the `address.number` is **1233**.  
**Hint:** Use dot notation to match `address.number` exactly.

**Solution:**
```javascript
db.businesses.find({ "address.number": 1233 })
```

---

### 2️⃣2️⃣ List the `business_name` of businesses whose `sector` contains the word **"Contractor"**.  
**Hint:** Use a regex with the `$regex` operator on the `sector` field.

**Solution:**
```javascript
db.businesses.find(
  { sector: { $regex: "Contractor" } },
  { business_name: 1, _id: 0 }
)
```

---

### 2️⃣3️⃣ Find businesses where the `address.city` is either **"RIDGEWOOD"** or **"NEW YORK"**.  
**Hint:** Use `$in` operator to match multiple cities.

**Solution:**
```javascript
db.businesses.find({
  "address.city": { $in: ["RIDGEWOOD", "NEW YORK"] }
})
```

---

### 2️⃣4️⃣ Retrieve the `business_name`, `date`, and `result` for all businesses with a `certificate_number` less than **7000000**.  
**Hint:** Use `$lt` for filtering and projection to select fields.

**Solution:**
```javascript
db.businesses.find(
  { certificate_number: { $lt: 7000000 } },
  { business_name: 1, date: 1, result: 1, _id: 0 }
)
```

---

### 2️⃣5️⃣ Find all documents sorted by `date` in **ascending order**.  
**Hint:** Use `sort()` with `1` for ascending order.

**Solution:**
```javascript
db.businesses.find().sort({ date: 1 })
```

---

### 2️⃣6️⃣ List the `id` values of businesses with the result **"No Violation Issued"**.  
**Hint:** Use projection and a filter on `result`.

**Solution:**
```javascript
db.businesses.find(
  { result: "No Violation Issued" },
  { id: 1, _id: 0 }
)
```

---

### 2️⃣7️⃣ Retrieve all documents where the `address.street` is **"MENAHAN ST"**.  
**Hint:** Use dot notation for nested `street` field matching.

**Solution:**
```javascript
db.businesses.find({ "address.street": "MENAHAN ST" })
```

---

### 2️⃣8️⃣ Find businesses whose `business_name` contains the word **"GROCERY"**.  
**Hint:** Use a case-insensitive regex search on `business_name`.

**Solution:**
```javascript
db.businesses.find(
  { business_name: { $regex: "GROCERY", $options: "i" } }
)
```

---

### 2️⃣9️⃣ List all businesses where the `sector` is **not** **"Tax Preparers - 891"**.  
**Hint:** Use `$ne` operator to exclude a specific value.

**Solution:**
```javascript
db.businesses.find({ sector: { $ne: "Tax Preparers - 891" } })
```

---

### 3️⃣0️⃣ Retrieve documents sorted by `certificate_number` in **descending order**.  
**Hint:** Use `sort()` with `-1` for descending order.

**Solution:**
```javascript
db.businesses.find().sort({ certificate_number: -1 })
```

---

### 3️⃣1️⃣ Find the number of businesses for each unique **result** type.  
**Hint:** Use `$group` to group by `result` and `$count` or `$sum` to total them.

**Solution:**
```javascript
db.businesses.aggregate([
  { $group: { _id: "$result", count: { $sum: 1 } } }
])
```

---

### 3️⃣2️⃣ List all businesses along with their `business_name` and `address.city`, sorted by `certificate_number` in **ascending order**.  
**Hint:** Use `find()` with projection and `sort()`.

**Solution:**
```javascript
db.businesses.find(
  {},
  { business_name: 1, "address.city": 1, _id: 0 }
).sort({ certificate_number: 1 })
```

---

### 3️⃣3️⃣ Find all businesses inspected in **"QUEENS VLG"** that received a **"Violation Issued"** result.  
**Hint:** Use `$and` or multiple conditions in `find()`.

**Solution:**
```javascript
db.businesses.find({
  "address.city": "QUEENS VLG",
  result: "Violation Issued"
})
```

---

### 3️⃣4️⃣ Count how many businesses belong to the sector **"Home Improvement Contractor - 100"**.  
**Hint:** Use `countDocuments()` with a filter.

**Solution:**
```javascript
db.businesses.countDocuments({
  sector: "Home Improvement Contractor - 100"
})
```

---

### 3️⃣5️⃣ Find the average `address.number` for businesses in **"QUEENS VLG"**.  
**Hint:** Use `$match` followed by `$group` with `$avg`.

**Solution:**
```javascript
db.businesses.aggregate([
  { $match: { "address.city": "QUEENS VLG" } },
  { $group: { _id: null, avgNumber: { $avg: "$address.number" } } }
])
```

---

### 3️⃣6️⃣ List distinct `address.city` values where `result` is **"Violation Issued"**.  
**Hint:** Use `distinct()` with a filter.

**Solution:**
```javascript
db.businesses.distinct(
  "address.city",
  { result: "Violation Issued" }
)
```

---

### 3️⃣7️⃣ Find the earliest inspection `date` recorded in the collection.  
**Hint:** Sort by `date` in ascending order and use `limit(1)`.

**Solution:**
```javascript
db.businesses.find().sort({ date: 1 }).limit(1)
```

---

### 3️⃣8️⃣ Retrieve the top **3 businesses** with the highest `certificate_number`.  
**Hint:** Sort by `certificate_number` in descending order and use `limit(3)`.

**Solution:**
```javascript
db.businesses.find().sort({ certificate_number: -1 }).limit(3)
```

---

### 3️⃣9️⃣ Count how many businesses have `address.zip` codes greater than **11000**.  
**Hint:** Use `$gt` in `countDocuments()`.

**Solution:**
```javascript
db.businesses.countDocuments({
  "address.zip": { $gt: 11000 }
})
```

---

### 4️⃣0️⃣ Group businesses by **sector** and count how many businesses belong to each sector.  
**Hint:** Use `$group` with `$sum`.

**Solution:**
```javascript
db.businesses.aggregate([
  { $group: { _id: "$sector", count: { $sum: 1 } } }
])
```

---

### 4️⃣1️⃣ Find businesses where the `address.street` contains the word **"ST"** and `result` is **"No Violation Issued"**.  
**Hint:** Use a regular expression (`$regex`) for the street and match with `result`.

**Solution:**
```javascript
db.businesses.find({
  "address.street": { $regex: "ST" },
  result: "No Violation Issued"
})
```

---

### 4️⃣2️⃣ Update the `result` to **"Pending"** for all businesses where the `result` is currently **"No Violation Issued"**.  
**Hint:** Use `updateMany()` with `$set`.

**Solution:**
```javascript
db.businesses.updateMany(
  { result: "No Violation Issued" },
  { $set: { result: "Pending" } }
)
```

---

### 4️⃣3️⃣ Delete all businesses with a `certificate_number` less than **6000000**.  
**Hint:** Use `deleteMany()` with `$lt`.

**Solution:**
```javascript
db.businesses.deleteMany({
  certificate_number: { $lt: 6000000 }
})
```

---

### 4️⃣4️⃣ Find businesses inspected in **"Feb 2015"** and list their `business_name` and `result`.  
**Hint:** Use `$regex` for the date string and projection.

**Solution:**
```javascript
db.businesses.find(
  { date: { $regex: "^Feb.*2015" } },
  { business_name: 1, result: 1, _id: 0 }
)
```

---

### 4️⃣5️⃣ Find all businesses whose `address.number` is between **8000 and 9500**.  
**Hint:** Use `$gte` and `$lte` operators in `find()`.

**Solution:**
```javascript
db.businesses.find({
  "address.number": { $gte: 8000, $lte: 9500 }
})
```

---

### 4️⃣6️⃣ Retrieve the list of businesses, projecting only `business_name`, `result`, and `address.zip`, sorted by `address.zip`.  
**Hint:** Use `find()` with projection and `sort()`.

**Solution:**
```javascript
db.businesses.find(
  {},
  { business_name: 1, result: 1, "address.zip": 1, _id: 0 }
).sort({ "address.zip": 1 })
```

---

### 4️⃣7️⃣ Find documents where the `address.zip` is either **11385** or **11427**.  
**Hint:** Use `$in` inside `find()`.

**Solution:**
```javascript
db.businesses.find({
  "address.zip": { $in: [11385, 11427] }
})
```

---

### 4️⃣8️⃣ Count how many unique `certificate_number` values exist in the collection.  
**Hint:** Use `distinct()` on `certificate_number` and then get the length.

**Solution:**
```javascript
db.businesses.distinct("certificate_number").length
```

---

### 4️⃣9️⃣ List the businesses where the `business_name` contains **"INC"** (case insensitive).  
**Hint:** Use `$regex` with `i` (ignore case).

**Solution:**
```javascript
db.businesses.find({
  business_name: { $regex: "INC", $options: "i" }
})
```

---

### 5️⃣0️⃣ Find businesses whose `sector` ends with **"100"**.  
**Hint:** Use `$regex` for matching strings ending with "100".

**Solution:**
```javascript
db.businesses.find({
  sector: { $regex: "100$" }
})
```

---

## Hard Questions (51–60)
---

### 5️⃣1️⃣ Group businesses by `address.city` and calculate the average `certificate_number` for each city.  
**Hint:** Use `$group` to group by city and `$avg` to calculate average.

**Solution:**
```javascript
db.businesses.aggregate([
  { $group: {
      _id: "$address.city",
      avgCertificate: { $avg: "$certificate_number" }
  }}
])
```

---

### 5️⃣2️⃣ Find the top 2 `sectors` with the highest number of **"Violation Issued"** results.  
**Hint:** Filter with `$match`, group with `$group`, sort with `$sort`, and limit with `$limit`.

**Solution:**
```javascript
db.businesses.aggregate([
  { $match: { result: "Violation Issued" } },
  { $group: {
      _id: "$sector",
      count: { $sum: 1 }
  }},
  { $sort: { count: -1 } },
  { $limit: 2 }
])
```

---

### 5️⃣3️⃣ Retrieve the `business_name` of the business with the latest `inspection date`.  
**Hint:** Sort by date descending and limit to 1.

**Solution:**
```javascript
db.businesses.find(
  {},
  { business_name: 1, _id: 0 }
).sort({ date: -1 }).limit(1)
```

---

### 5️⃣4️⃣ Group businesses by `sector` and `result`, then count how many businesses fall into each combination.  
**Hint:** Use `$group` with multiple fields in `_id`.

**Solution:**
```javascript
db.businesses.aggregate([
  { $group: {
      _id: { sector: "$sector", result: "$result" },
      count: { $sum: 1 }
  }}
])
```

---

### 5️⃣5️⃣ Find the percentage of businesses that received a **"Violation Issued"** result out of the total businesses.  
**Hint:** Use `$group` to count both total and violation counts, then compute percentage in code.

**Solution:**
```javascript
var total = db.businesses.count();
var violations = db.businesses.count({ result: "Violation Issued" });
var percentage = (violations / total) * 100;
print(percentage + "%");
```

---

### 5️⃣6️⃣ List businesses that have the same `address.zip` but different `result` values.  
**Hint:** Use `$group` to collect distinct results by zip, and filter groups with multiple results.

**Solution:**
```javascript
db.businesses.aggregate([
  { $group: {
      _id: "$address.zip",
      resultTypes: { $addToSet: "$result" }
  }},
  { $match: { "resultTypes.1": { $exists: true } } }
])
```

---

### 5️⃣7️⃣ Retrieve businesses whose `address.number` is higher than the average `address.number` of all businesses.  
**Hint:** First compute the average, then use `$match` with `$gt`.

**Solution:**
```javascript
var avgNumber = db.businesses.aggregate([
  { $group: { _id: null, avgNumber: { $avg: "$address.number" } } }
]).toArray()[0].avgNumber;

db.businesses.find({ "address.number": { $gt: avgNumber } })
```

---

### 5️⃣8️⃣ For each `address.city`, count how many businesses have a `certificate_number` above **7000000**.  
**Hint:** Use `$match`, then `$group` with a count.

**Solution:**
```javascript
db.businesses.aggregate([
  { $match: { certificate_number: { $gt: 7000000 } } },
  { $group: {
      _id: "$address.city",
      count: { $sum: 1 }
  }}
])
```

---

### 5️⃣9️⃣ Find businesses with duplicate `certificate_number` values (if any).  
**Hint:** Group by `certificate_number` and filter where count > 1.

**Solution:**
```javascript
db.businesses.aggregate([
  { $group: {
      _id: "$certificate_number",
      count: { $sum: 1 }
  }},
  { $match: { count: { $gt: 1 } } }
])
```

---

### 6️⃣0️⃣ Group businesses by the **month** of the `date` and count how many inspections happened in each month.  
**Hint:** Use `$group` and `$substr` to extract month from the date string.

**Solution:**
```javascript
db.businesses.aggregate([
  { $group: {
      _id: { $substr: ["$date", 0, 3] },
      count: { $sum: 1 }
  }}
])
```

---
