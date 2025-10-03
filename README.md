# MongoDB Practice - Business Inspection Dataset

A comprehensive MongoDB practice project using a business inspection dataset with 60 practical questions ranging from basic queries to advanced aggregation operations.

## 📋 Project Overview

This project provides hands-on MongoDB practice using real-world business inspection data from New York City. It includes structured practice questions, detailed solutions with explanations, and Jupyter notebooks for interactive learning.

## 📁 Project Structure

```
├── Questions.md              # 60 MongoDB practice questions (Easy, Medium, Hard)
├── solutions_with_hints.md   # Detailed solutions with hints and explanations
├── Setup.ipynb              # MongoDB setup and data loading notebook
├── Solutions.ipynb          # Interactive solutions in Jupyter notebook format
├── city_inspections.json    # Business inspection dataset (81,048 documents)
└── Readme.md               # Project documentation
```

## 🗃️ Dataset Information

**File:** `city_inspections.json`
- **Documents:** 81,048 business inspection records
- **Source:** New York City business inspections
- **Data Structure:**
  ```json
  {
    "_id": {"$oid": "..."},
    "id": "inspection_id",
    "certificate_number": 1234567,
    "business_name": "BUSINESS NAME",
    "date": "Feb 20 2015",
    "result": "No Violation Issued",
    "sector": "Business Category",
    "address": {
      "city": "CITY NAME",
      "zip": 12345,
      "street": "STREET NAME",
      "number": 1234
    }
  }
  ```

## 🎯 Practice Questions Categories

### Easy Questions (1-30)
- Basic queries and filtering
- Field projection
- Simple comparison operators
- Sorting and counting

### Medium Questions (31-50)
- Aggregation pipelines
- Grouping and counting
- Complex filtering
- Text search operations

### Hard Questions (51-60)
- Advanced aggregation
- Complex data transformations
- Multi-stage pipelines
- Performance optimization

## 🚀 Getting Started

### Prerequisites
- MongoDB installed locally or MongoDB Atlas account
- Python with PyMongo library
- Jupyter Notebook/Lab

### Setup Instructions

1. **Clone/Download the project files**

2. **Set up MongoDB connection:**
   - Start your local MongoDB instance, or
   - Configure MongoDB Atlas connection

3. **Load the dataset:**
   ```bash
   mongoimport --db business_inspections --collection inspections --file city_inspections.json
   ```

4. **Run the Setup notebook:**
   - Open `Setup.ipynb`
   - Follow the setup instructions
   - Verify data loading

5. **Start practicing:**
   - Review questions in `Questions.md`
   - Try solving them independently
   - Check solutions in `solutions_with_hints.md` or `Solutions.ipynb`

## 📚 Learning Path

1. **Start with Easy Questions (1-30)**
   - Master basic MongoDB query syntax
   - Learn filtering and projection
   - Practice sorting and limiting results

2. **Progress to Medium Questions (31-50)**
   - Understand aggregation framework
   - Learn grouping and statistical operations
   - Practice complex queries

3. **Challenge yourself with Hard Questions (51-60)**
   - Master advanced aggregation pipelines
   - Learn optimization techniques
   - Practice real-world scenarios

## 💡 Key Learning Objectives

- **Basic Operations:** find(), projection, sorting, limiting
- **Query Operators:** $eq, $ne, $gt, $lt, $in, $regex
- **Aggregation Framework:** $match, $group, $sort, $project, $unwind
- **Text Operations:** $regex, $text search
- **Statistical Operations:** $sum, $avg, $count, $min, $max
- **Advanced Techniques:** Indexing, performance optimization

## 🔧 Tools & Technologies

- **Database:** MongoDB
- **Programming:** Python with PyMongo
- **Environment:** Jupyter Notebooks
- **Data Format:** JSON

## 📖 Usage Examples

**Basic Query:**
```javascript
db.inspections.find({"result": "Violation Issued"})
```

**Aggregation Pipeline:**
```javascript
db.inspections.aggregate([
  {"$group": {"_id": "$result", "count": {"$sum": 1}}},
  {"$sort": {"count": -1}}
])
```

**Python with PyMongo:**
```python
collection.find({"address.city": "NEW YORK"})
```

## 🎓 Skills Developed

- MongoDB query construction
- Aggregation pipeline design
- Data analysis with NoSQL
- Python database programming
- Performance optimization
- Real-world data handling

## 📊 Dataset Statistics

- **Total Records:** 81,048
- **Unique Businesses:** ~40,000+
- **Cities Covered:** 100+
- **Business Sectors:** 50+
- **Date Range:** 2015 inspections
- **Results Types:** Violation Issued, No Violation Issued, Pass, etc.

## 🤝 Contributing

Feel free to:
- Add more practice questions
- Improve existing solutions
- Share alternative approaches
- Report issues or suggestions

## 📝 Sources

- **Questions:** Generated with ChatGPT for comprehensive MongoDB practice
- **Dataset:** [MongoDB Datasets Repository](https://github.com/ozlerhakan/mongodb-json-files/tree/master/datasets)
- **Inspiration:** Real-world business inspection data from NYC Open Data

---

**Happy Learning!** 🚀 Master MongoDB through hands-on practice with real-world data.