# Emmanuel Ocheme Owoicho Palm Oil — website starter

This is a starter Django website for a palm-oil shop. It is a development project, not yet ready for public production use.

## 1. Install Python
Install Python 3.11 or newer from https://www.python.org/downloads/ . During Windows installation, tick **Add Python to PATH**.

## 2. Open a terminal in this folder
Create and activate a virtual environment:

**Windows (Command Prompt):**
```bat
py -m venv .venv
.venv\Scripts\activate
```

**Mac/Linux:**
```bash
python3 -m venv .venv
source .venv/bin/activate
```

Install Django and create the database:
```bash
python -m pip install -r requirements.txt
python manage.py makemigrations store
python manage.py migrate
python manage.py createsuperuser
python manage.py runserver
```

Open http://127.0.0.1:8000/ to view the site and http://127.0.0.1:8000/admin/ to manage products. The terminal will show the admin login prompts when you create the superuser.

## 3. Add your products
In `/admin/`, add each bottle/gallon size as a separate Product. Enter the product name, size, price in naira, stock count, description, and optional image URL.

## 4. Connect WhatsApp
Open `store/views.py` and replace `WHATSAPP_BUSINESS_NUMBER = '2340000000000'` with your WhatsApp Business number in international format using digits only. For example, Nigerian numbers begin with `234`, without the leading `+` or the first `0`. The placeholder number is not a real business contact.

## Current features
- Responsive home, shop, story, and contact pages
- Product catalogue managed through Django admin
- Session-based cart and quantity updates
- WhatsApp click-to-chat order message containing cart items and total
- Basic Order model and admin list for the next development stage
- SQLite local development database

## Not implemented yet
- Card/bank payments or Paystack verification
- Customer checkout form and customer accounts
- Automatic order creation from WhatsApp/cart
- Delivery tracking interface
- Production deployment, PostgreSQL, email, security hardening, and real product photography

Never put Paystack secret keys in frontend code or commit them to source control. Payment integration must verify transactions on the server before marking an order as paid. Before launch, set a secure `SECRET_KEY`, `DEBUG = False`, allowed hosts, HTTPS, backups, and production database settings.
