# FAQ Backend API

🚀 Project Overview
This is a Django-based REST API for managing Frequently Asked Questions (FAQs) with multi-language translation support. 
The API supports dynamic translations using Google Translate and caching with Redis(currently under debugging for full implementation). 
A WYSIWYG editor (CKEditor) allows formatting rich text answers in the admin panel.

🏗 Features
- ✅ **CRUD Operations** for FAQs
- ✅ **Multi-language Support** (English, Hindi, Bengali)
- ✅ **Google Translate API Integration**
- ✅ **Rich Text Editing (WYSIWYG)**
- 🔴 **Redis Caching** (Implemented but under debugging)
- ✅ **Django Admin Panel** for FAQ management
- ✅ **Unit Testing with Pytest**

---
 🛠 Installation & Setup
 1️⃣ Clone the Repository
 
git clone https://github.com/jagrattt23/FAQ-Django.git
cd FAQ-Django


2️⃣ Create a Virtual Environment

python -m venv venv
source venv/bin/activate  # Mac/Linux
venv\Scripts\activate    # Windows


3️⃣ Install Dependencies

pip install -r requirements.txt


4️⃣ Set Up Environment Variables
Create a .env file in the project root and add:
sh
SECRET_KEY=your_django_secret_key
DEBUG=True


5️⃣ Apply Migrations & Start Server

python manage.py migrate
python manage.py runserver

API is now running at: http://127.0.0.1:8000/

---

⚡ API Endpoints
🔹 Fetch All FAQs
GET /api/faqs/
json
{
  "id": 1,
  "question": "What is Django?",
  "answer": "Django is a web framework.",
  "language": "en"
}


🔹 Create a New FAQ POST -- /api/faqs/
json
{
  "question": "What is Python?",
  "answer": "Python is a programming language.",
  "language": "en"
}


🔹 Get FAQs in a Specific Language -- GET/api/faqs/?lang=hi`
json
{
  "question": "Python क्या है?",
  "answer": "Python एक प्रोग्रामिंग भाषा है।"
}


🔹 Update an FAQ**
PUT  /api/faqs/{id}/

🔹 Delete an FAQ
DELETE /api/faqs/{id}/

---

🛑 Redis Caching (⚠️ Known Issue)
Redis caching was implemented to store FAQ responses for faster retrieval, but it is currently facing issues.

#Steps Taken:
1. Django Redis Cache Framework** was configured.
2. FAQs were stored in Redis** for improved performance.
3. Issue: Cache data isn't persisting or being retrieved as expected.

Temporary Workaround:
- The API still functions without Redis**, but responses may be slightly slower.
- The issue is under debugging and will be resolved in future updates.

Running Redis (if debugging further):

brew install redis  # MacOS
sudo apt install redis  # Ubuntu
redis-server

To flush the cache:
redis-cli FLUSHALL


---

🔍 Testing with Pytest
Run Unit Tests

pytest faq/tests/ -v

✅ All tests should pass (except for potential Redis-dependent tests).

---

📜 Contribution Guidelines
1. Fork the repository
2. create a feature branch

git checkout -b feat/your-feature

3. Follow commit message conventions**

git commit -m "feat: Add new API endpoint for FAQs"

4. Submit a pull request

---

📝 Version Control & Git Best Practices
We follow **conventional commit messages**:
- feat: New feature
- fix: Bug fix
- docs: Documentation update
- refactor: Code improvement without feature change
- test: Unit test additions

Example commits:

git commit -m "feat: Add multilingual FAQ model"
git commit -m "fix: Improve translation caching"
git commit -m "docs: Update README with API examples"


---

📌 Future Improvements
- ✅ Fix Redis caching for faster API responses
- ✅ Add Docker & Deployment Instructions


---

📞 Contact
For queries, contact: jagratmalviya99@gmail.com

Happy coding! 🚀

