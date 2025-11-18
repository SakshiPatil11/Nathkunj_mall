# Nathkunj Agri Mall — Vegetable Mall Management (HTML/CSS/JS)

A fully responsive, modern front‑end website for Nathkunj Agri Mall with customer, admin, and delivery partner modules. Built using HTML, CSS, and vanilla JavaScript.

## Features
- Customer: Home, About, Products, Farmers (registration), Cart, Checkout, Contact, Login/Signup
- Products: Grid with 12+ vegetables, search, category filter, Add to Cart
- Cart: Quantity update, remove items, grand total, payment options (COD, UPI, Card)
- Forms: Client-side validation for contact and farmer registration
- Auth: Client-side signup/login (password hash via SHA‑256) for demo use
- Admin: Dashboard, Add Product (with image upload), Manage Products, Manage Orders (status + assign), Manage Users, Reports (CSV export, print)
- Delivery Partner: Login, view assigned orders, update status, route navigation via Google Maps link

## Tech Stack
- HTML5, CSS3 (Flexbox + Grid), JavaScript (vanilla)
- LocalStorage for demo persistence
- Optional MySQL schema provided for backend implementation

## Getting Started
1. Clone the repository
2. Open `index.html` in a browser
3. Or run a simple local server:
   - VS Code: use Live Server
   - Python: `python -m http.server 8000` then open `http://localhost:8000/`

## Project Structure
```
.
├─ index.html
├─ about.html
├─ products.html
├─ farmers.html
├─ cart.html
├─ contact.html
├─ login.html
├─ signup.html
├─ admin/
│  ├─ dashboard.html
│  ├─ add-product.html
│  ├─ manage-products.html
│  ├─ manage-orders.html
│  ├─ manage-users.html
│  └─ reports.html
├─ delivery/
│  ├─ login.html
│  └─ orders.html
├─ assets/
│  ├─ style.css
│  └─ script.js
├─ images/
│  ├─ leafy.svg
│  ├─ root.svg
│  └─ seasonal.svg
└─ db/
   └─ schema.sql
```

## Pages
- Customer: `index.html`, `about.html`, `products.html`, `farmers.html`, `cart.html`, `contact.html`, `login.html`, `signup.html`
- Admin: `admin/dashboard.html`, `admin/add-product.html`, `admin/manage-products.html`, `admin/manage-orders.html`, `admin/manage-users.html`, `admin/reports.html`
- Delivery Partner: `delivery/login.html`, `delivery/orders.html`

## Demo Data & Storage
- Products, Cart, Orders, Wishlist are stored in `localStorage` for a front‑end only demo.
- Admin “Add Product” saves new items (including uploaded images as DataURLs) to `localStorage`.
- Checkout records orders, updates product stock, and exposes them in Admin → Manage Orders.

## Add Your Own Images
- Place images in `images/` (e.g., `images/tomato.jpg`).
- Update product entries in `assets/script.js` → `loadProducts()` to point to your filenames.
- Or use Admin → Add Product to upload an image (stored as DataURL) and add items without editing code.

## Admin & Delivery Flow (Demo)
- Admin Dashboard: sales summary and low-stock alerts (≤ 10 kg)
- Manage Orders: update status to Packed / Out for Delivery / Delivered and assign a partner ID
- Delivery Login: enter Partner ID, see assigned orders, update status, open route in Google Maps

## Optional Backend (MySQL)
- A MySQL schema is provided at `db/schema.sql` for real persistence and server-side features.
- Create the database using your MySQL credentials:
  - `mysql -u root -p` (password: your MySQL password)
  - `SOURCE <absolute-path-to>/db/schema.sql;`
- Tables: `users`, `admins`, `products`, `categories`, `orders`, `order_items`, `delivery_addresses`, `reviews`, `coupons`, `sales_reports`, `delivery_partners`
- Recommended: implement server-side auth (bcrypt), product CRUD, order lifecycle, and delivery assignment using Node.js/Express, PHP, or similar.

## Development Notes
- This project is front‑end only. Do not store real payment or sensitive data in `localStorage`.
- To move to production, add a backend and replace `localStorage` reads/writes with API calls.

## License
- Proprietary. Usage restricted to Nathkunj Agri Mall unless otherwise permitted.
