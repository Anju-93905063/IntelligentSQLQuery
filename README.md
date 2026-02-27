# IntelliSQL: Intelligent SQL Querying with LLMs Using Gemini AI

## 📌 Project Overview

**IntelliSQL** is an intelligent SQL querying application that allows users to:
- Ask questions in plain English
- Convert those questions into SQL queries using a generative AI model
- Execute SQL on a SQLite database
- Display results in a friendly web interface

This project demonstrates the power of combining Natural Language Processing (NLP), Generative AI (Google Gemini), and interactive UI using Streamlit.

---

<img width="1364" height="680" alt="home_page" src="https://github.com/user-attachments/assets/9e2b5888-40b4-4006-8ebe-d4f5c932bade" />

## 🚀 Features

✔ Natural language to SQL conversion  
✔ Auto-generated SQL execution  
✔ Display results in tabular form  
✔ Supports aggregation, filtering, and analytical queries  
✔ Secure API key management  
✔ Simple and interactive UI with Streamlit  

---
<img width="1365" height="681" alt="query_assisstance" src="https://github.com/user-attachments/assets/067fc42a-668a-40af-a3b3-ab449d15ad43" />

![Uploading query_result.png…]()

## 📂 Project Structure

```
Intelligent-SQL-Querying-with-LLMs-Using-Gemini-Pro/
│
├── app.py                # Main Streamlit app
├── sql.py                # Database creation script
├── data.db               # SQLite database file
├── requirements.txt      # Python dependencies
├── .env                  # Environment file containing API_KEY (ignore in git)
└── README.md             # Project documentation
```

---

## 🛠 Technologies Used

- Python 3.10+
- Streamlit
- SQLite3
- Google Generative AI (Gemini Model)
- python-dotenv

---

## ⚙️ Installation & Setup

### 1️⃣ Clone the Repository

```bash
git clone https://github.com/Anju-93905063/IntelligentSQLQuery
cd IntelligentSQLQuery
```

---

### 2️⃣ Install Dependencies

```bash
pip install -r requirements.txt
```

This installs:

```
streamlit
google-generativeai
python-dotenv
```

---

### 3️⃣ Set Up API Key

Create a file named `.env` in the project root:

```
API_KEY=your_google_gemini_api_key_here
```

💡 Make sure:
- You do **not** push `.env` to GitHub
- This file is included in `.gitignore`

---

## 📌 Create & Populate SQLite Database

Run:

```bash
python sql.py
```

This script will:
- Create the SQLite database file `data.db`
- Create the table `STUDENTS`
- Insert sample records

---

## 📌 Running the Application

```bash
streamlit run app.py
```

Your default browser will open the IntelliSQL interface.

---

## 🧠 How It Works

1. **User Input:**  
   User enters an English question like:
   > “Show students working at INFOSYS”

2. **AI Translation:**  
   The prompt and question are sent to the Gemini AI model.

3. **SQL Generation:**  
   AI returns a valid SQL query, e.g.:
   ```sql
   SELECT * FROM STUDENTS WHERE COMPANY="INFOSYS";
   ```

4. **Execution:**  
   Query is executed on the SQLite database.

5. **Display:**  
   Results are shown in a table.

---

## 📌 Example Queries

| English Question | SQL Generated |
|------------------|---------------|
| How many records? | `SELECT COUNT(*) FROM STUDENTS;` |
| Average marks | `SELECT AVG(MARKS) FROM STUDENTS;` |
| Highest scorer | `SELECT * FROM STUDENTS WHERE MARKS=(SELECT MAX(MARKS) FROM STUDENTS);` |
| Students in MCom | `SELECT * FROM STUDENTS WHERE CLASS="MCom";` |

---

## 🔐 API Key Configuration (Secure)

1. Create API key from Google AI Studio.  
2. Restrict key to **Generative Language API** only.  
3. No application restrictions (for local use).  
4. Store the key in `.env`.

📌 Sample restrictive configuration:

```
Application restrictions: None
API restrictions: Restricted to Generative Language API
```

---

## 🧠 Model Configuration

In your code, use the following stable model:

```python
model = genai.GenerativeModel("models/gemini-1.0-pro")
```

This is the most stable and supported model name with the current API.

---

## 🧪 Common Errors & Fixes

| Error | Fix |
|-------|-----|
| `403 leaked key` | Delete old key, create new restricted key |
| `model not found` | Use `models/gemini-1.0-pro` |
| API Key not read | Make sure `.env` exists and you called `load_dotenv()` |
| No API Key error | Confirm key is in environment variables |

---

## 📊 Database Schema

### Table: STUDENTS

| Column | Type |
|--------|------|
| NAME    | TEXT |
| CLASS   | TEXT |
| MARKS   | INTEGER |
| COMPANY | TEXT |

Sample entries are added in `sql.py`.

---

## 🚀 Future Enhancements

- Support multiple tables
- Add query validation
- Add SQL explain plan feature
- Deploy on cloud server
- Support PostgreSQL/MySQL option

---


---

## 🎯 Conclusion

IntelliSQL simplifies database querying by leveraging Generative AI to translate natural language into SQL. This project is an example of modern AI-powered tools empowering users to interact with data easily and effectively.
