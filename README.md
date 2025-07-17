# TECMEX Restaurant Ordering System

## Project Overview
TECMEX is a full-stack restaurant ordering system. This is the first branch in India, located in Sarita Vihar, New Delhi. The system allows users to browse the menu, place orders, book tables, and manage orders online. It features Indian Rupee pricing, Indian phone validation, and a modern, responsive UI.

## Setting Up the Project

### Frontend
```
cd frontend
npm install
npm run serve
```

### Backend
```
cd backend
npm install
npm start
```

### Build for Production
```
cd frontend
npm run build
```

## Database Schema

The main tables are as follows (see `frontend/src/resources/db_restaurant.sql` for full details):

- **food**: Stores menu items
- **user**: Stores user accounts
- **cart**: Stores user cart items
- **booktable**: Stores table bookings
- **billdetails**: Stores bill item details
- **billstatus**: Stores bill status and payment info

Example (food table):
```sql
CREATE TABLE food( 
    food_id INT(11) PRIMARY KEY AUTO_INCREMENT, 
    food_name VARCHAR(255), 
    food_star VARCHAR(255),
    food_vote VARCHAR(255),
    food_price VARCHAR(255),
    food_discount VARCHAR(255),
    food_desc VARCHAR(255),
    food_status VARCHAR(255),
    food_type VARCHAR(255),
    food_category VARCHAR(255),
    food_src VARCHAR(255)
) ENGINE=INNODB;
```

## API Endpoints

All endpoints are prefixed with `/api/`.

- `GET   /api/foods` — List all foods
- `GET   /api/foods/:id` — Get food by ID
- `POST  /api/foods` — Add new food
- `PUT   /api/foods/:id` — Update food
- `DELETE /api/foods/:id` — Delete food

- `GET   /api/users/:email` — Get user by email
- `POST  /api/users/` — Create user account

- `POST  /api/cartItem` — Add item to cart
- `GET   /api/cartItem/:user_id` — Get cart items for user
- `PUT   /api/cartItem` — Update cart item quantity
- `DELETE /api/cartItem/:user_id/:food_id` — Remove item from cart
- `DELETE /api/cartItems/:user_id` — Clear cart for user

- `POST  /api/booking` — Book a table

- `POST  /api/billdetails` — Add bill details
- `GET   /api/billdetails/:bill_id` — Get bill details by bill ID

- `POST  /api/billstatus` — Create bill status
- `GET   /api/billstatus` — Get all bills
- `GET   /api/billstatus/user/:user_id` — Get all bills for a user
- `GET   /api/billstatus/bill/:bill_id` — Get bill status by bill ID
- `PUT   /api/billstatus/:bill_id` — Update bill status
- `PUT   /api/billstatus/paid/:bill_id` — Mark bill as paid
- `PUT   /api/billstatus/cancel/:bill_id` — Cancel bill

## Directory Structure

```
restaurant-ordering-system/
├── backend/
│   ├── config/           # Database config
│   ├── controllers/      # Express controllers
│   ├── models/           # Database models
│   ├── routes/           # API routes
│   ├── restaurant_management/ # Static/build assets
│   └── index.js          # Backend entry point
├── frontend/
│   ├── public/           # Static frontend assets
│   ├── src/
│   │   ├── admin/        # Admin pages
│   │   ├── assets/       # Images, CSS
│   │   ├── components/   # Vue components
│   │   ├── pages/        # Main user-facing pages
│   │   ├── resources/    # SQL schema
│   │   ├── router/       # Vue router
│   │   ├── store/        # Vuex store
│   │   └── App.vue       # Main app
│   └── package.json      # Frontend dependencies
├── README.md             # Project documentation

```

