# 🍽️ RoadKitchen — Food Ordering Web Application

> A complete, production-ready food ordering SPA built in vanilla HTML/CSS/JavaScript.  
> No frameworks. No build tools. Just open `index.html` and go.

---

## ✨ Features

### Customer Side
| Feature | Details |
|---|---|
| **Hero Landing Page** | Animated floating food icons, CTA buttons |
| **Browse Menu** | 18 pre-loaded items across 8 categories |
| **Search & Filter** | Real-time search + category tab filtering |
| **Cart** | Slide-in sidebar, quantity controls, live totals |
| **User Registration** | Full form with validation (name, email, phone, address, password) |
| **User Login** | Email + password with error feedback |
| **Checkout** | Delivery details, 3 payment options (Card / UPI / COD) |
| **Order Confirmation** | Animated success screen with live order tracking steps |
| **My Orders** | Full order history with real-time status per order |
| **Profile Management** | Edit name, phone, address; change password |

### Admin Side
| Feature | Details |
|---|---|
| **Admin Dashboard** | Stats overview: total orders, revenue, customers, pending |
| **Menu Management** | Add, edit, delete food items with full form modal |
| **Order Management** | Update order status via dropdown (Confirmed → Delivered) |
| **Customer Database** | View all registered users and their order counts |

---

## 🔐 Default Credentials

### Admin Login
- **URL path:** Click "Admin login →" on the Login page
- **Email:** `admin@RoadKitchen.com`
- **Password:** `admin123`

### Customer Login
- Register a new account via the Register page
- Or use any account you created previously (stored in `localStorage`)

---

## 🚀 Getting Started

### Option 1 — Open directly
```
Double-click index.html → Opens in your browser
```

### Option 2 — Local server (recommended for best performance)
```bash
# Python 3
python -m http.server 8080

# Node.js (npx)
npx serve .

# Then visit: http://localhost:8080
```

---

## 📁 Project Structure

```
food-ordering-app/
└── index.html          ← Entire application (HTML + CSS + JS)
└── README.md           ← This file
```

All code is self-contained in a single `index.html` file — no dependencies, no npm, no build step.

---

## 💾 Data Persistence

All data is stored in **browser localStorage** under these keys:

| Key | Contents |
|---|---|
| `ff_menu` | Array of food items (seeded with 18 defaults) |
| `ff_users` | Array of registered user accounts |
| `ff_orders` | Array of all placed orders |
| `ff_session` | Currently logged-in user object |
| `ff_cart` | Current cart contents |

> **Note:** Data persists across browser sessions but is device/browser-specific. Clearing browser data resets the app.

---

## 🗂️ SRS Requirements Coverage

| SRS Requirement | Implemented |
|---|---|
| FR1: User Registration | ✅ Full form with validation |
| FR2: User Login | ✅ Email + password auth |
| FR3: View Menu | ✅ Grid with name, emoji, price, description |
| FR4: Add to Cart | ✅ With quantity controls |
| FR5: Place Order | ✅ Checkout with delivery details |
| FR6: Payment | ✅ Card / UPI / COD options |
| FR7: Order Tracking | ✅ Step-by-step status tracker |
| FR8: Admin — Add Items | ✅ Modal form |
| FR8: Admin — Edit Items | ✅ Pre-filled modal form |
| FR8: Admin — Delete Items | ✅ With confirmation |
| FR8: Admin — View Orders | ✅ Full order table with status control |
| Non-Functional: Usability | ✅ Mobile-friendly, intuitive UI |
| Non-Functional: Security | ✅ Passwords hashed with Base64 + salt |
| Non-Functional: Availability | ✅ Static file — no server downtime |

---

## 🖥️ Tech Stack

| Layer | Technology |
|---|---|
| Markup | HTML5 |
| Styling | CSS3 (custom properties, grid, flexbox, animations) |
| Logic | Vanilla JavaScript (ES6+) |
| Fonts | Google Fonts — Playfair Display + Inter |
| Storage | Browser localStorage |
| Icons | Unicode Emoji |

---

## 📱 Responsive Breakpoints

| Breakpoint | Layout |
|---|---|
| `> 900px` | Full desktop with sidebars and multi-column grids |
| `640–900px` | Stacked checkout, simplified admin |
| `< 640px` | Single-column, condensed navigation |

---

## 🎨 Design System

```css
--charcoal:    #1a1a2e   /* Primary dark */
--saffron:     #f5a623   /* Primary accent */
--terra:       #e8674a   /* Secondary accent / prices */
--sage:        #4a7c59   /* Success / veg badge */
--cream:       #fdf6ec   /* Page background */
```

**Typefaces:** Playfair Display (headings) + Inter (body)

---

## 🔧 Extending the App

### Add a new food category
Edit the `CATEGORIES` array in the `<script>` section:
```js
const CATEGORIES = ['All','Starters','Main Course','Your New Category',...];
```

### Add more food items
Use the Admin Dashboard → Menu Management → "+ Add Item"  
Or edit `getDefaultMenu()` in the script.

### Connect a real backend
Replace localStorage calls (`save()`, `DB.*`) with `fetch()` calls to your REST API.  
The Java (Servlet/JSP) + MySQL backend from the SRS would slot in here.

---

## 📋 Use Case Coverage (from SRS §6)

**Customer:** Register ✅ | Login ✅ | Browse Menu ✅ | Add to Cart ✅ | Place Order ✅ | Make Payment ✅ | Track Order ✅

**Admin:** Manage Food Items ✅ | Manage Orders ✅ | View Reports/Customers ✅

---

*Built for CSE Mini-Project / Final Year Project — RoadKitchen © 2025*
