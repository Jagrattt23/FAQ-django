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

🛠 Technologies Used

Django 5.1.5
Django REST Framework
Googletrans (for translation)
CKEditor (for rich text support)
Pytest (for testing)

---

⚡ API Endpoints

GET      -  /api/faqs/             ->  Get all FAQs
GET      -  /api/faqs/?lang=hi     ->  Get FAQs in Hindi
GET      -  /api/faqs/?lang=bn     ->  Get FAQs in Bengali
POST     -  /api/faqs/             ->  Create a new FAQ
PUT      -  /api/faqs/{id}/        ->  Update an FAQ
DELETE   -  /api/faqs/{id}/        ->  Delete an FAQ

Example Request:
POST /api/faqs/
{
    "question": "What is Django?",
    "answer": "Django is a web framework",
    "language": "en"
}
Example Response:
{
    "id": 1,
    "question": "What is Django?",
    "answer": "Django is a web framework",
    "language": "en",
    "question_hi": "Django क्या है?",
    "question_bn": "জ্যাঙ্গো কী?",
    "answer_hi": "Django एक वेब फ्रेमवर्क है",
    "answer_bn": "জ্যাঙ্গো একটি ওয়েব ফ্রেমওয়ার্ক"
}

---

🔍 Testing with Pytest
Run Unit Tests

pytest faq/tests/ -v

✅ All tests passed 

---

📝 Version Control & Git Best Practices
📌 Contribution Guidelines

Fork the Repository
Create a New Branch (feat-new-feature)
Commit Changes

git commit -m "feat: Add a new feature"
Push & Create a PR


---

⚠️ Limitations & Next Steps
Redis Caching is not implemented yet.
Docker Support is not available currently.

Running Redis (if debugging further):
brew install redis  # MacOS
sudo apt install redis  # Ubuntu
redis-server

To flush the cache:
redis-cli FLUSHALL

---

🎯 Future Improvements

✅ Implement Redis Caching for Performance
✅ Add Docker Support for Easy Deployment


---

👨‍💻 Author: Jagrattt23

Happy coding! 🚀

