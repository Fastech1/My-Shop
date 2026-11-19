# My-Shop
The Is a simple App for shop owners to track inventory and sales 

---

SHOP POS — DEVELOPMENT DOCUMENTATION

*Project Name:* Shop POS (Drink POS)
*Live URL:* https://myshop-orcin-eta.vercel.app/
*Deployment Platform:* Vercel
*Date Built:* November 18, 2026
*Version:* v1.0 — Mini POS for Small Shops
*Type:* Progressive Web App (PWA) — Installable on Android & iPhone

1. Project Overview

Shop POS is a free, mobile-first Point of Sale system for small shop owners in Nigeria.

It replaces a physical POS machine / paper notebook. A shop owner can sell, give a supermarket-style receipt, track stock, and record debts — all from a phone, with no signup and works offline.

Target users: Provision stores, drink shops, food vendors, phone accessory shops, boutiques, supermarkets (small).

2. Core Features Delivered
Feature	Description
**Sell Screen**	Tap products to add to cart, change quantity, see total automatically
**Sell by Pack or Piece**	Sell e.g. 1 pack of Coke or 1 piece of Coke, with different prices
**Inventory Management**	Add, edit, delete products. Track stock in Packs + Pieces
**Low Stock Alert**	Shows when a product is almost finished
**Checkout**	Supports Cash, Transfer, POS payment methods
**Discount**	Apply discount per sale e.g. ₦200 off
**Receipt Generation**	Auto-generates receipt with shop name, date, time, items, total
**Receipt as Image**	Download receipt as image with timestamp
**Debt Book**	Record customers who buy on credit, amount owed, mark as paid
**Sales History**	View today’s sales, past sales list
**Shop Settings**	Set shop name, phone number, address shown on receipt
**PWA Install**	Install to home screen, full-screen, no browser bar
**Offline Mode**	Works without internet, data saved on device
3. User Flow

*1. First Open*
- User opens link
- Sets Shop Name, Phone, Address in Settings
- App saves settings locally

*2. Add Products*
- Go to Items / Products
- Add: Name, Pack Price, Piece Price, Stock in Packs, Pieces per Pack
- Example: Indomie — Pack ₦12,000 — Piece ₦1,200 — Stock 5 Packs

*3. Sell*
- Go to Sell screen
- Tap product > Select Pack or Piece > Add to cart
- Adjust quantity + / -
- Select Payment: Cash / Transfer / POS
- Tap Checkout

*4. Receipt*
- Receipt appears with timestamp
- Options: Download as image / Share to customer

*5. Debt*
- If customer did not pay fully, add to Debt Book
- Enter customer name, amount owed
- Mark as Paid when they pay

4. Technical Architecture
Layer	Technology
**Frontend**	React / http://Next.js (JavaScript)
**Hosting**	Vercel
**Storage**	Browser LocalStorage (on-device only)
**PWA**	Web App Manifest + Service Worker for install + offline
**Receipt**	HTML to Image generation
**Styling**	Mobile-first, responsive design
*Data Model (LocalStorage):*

- *Products:* id, name, packPrice, piecePrice, stockPacks, piecesPerPack, stockPieces
- *Sales:* id, items[], total, paymentMethod, discount, date, time
- *Debts:* id, customerName, amount, amountPaid, status (Owed / Paid), date
- *Settings:* shopName, phone, address, currency (₦)

*No Backend:* There is currently no server database, no user login, no cloud sync. All data lives on the shop owner’s phone. If phone is cleared / lost, data is lost.

5. What Was Tested Yesterday

- Sell by Pack and Piece works correctly
- Stock reduces correctly after sale
- Receipt image downloads with correct shop name + timestamp
- Debt book adds and clears correctly
- App installs on Android (Add to Home Screen) and iPhone (Share > Add to Home Screen)
- App opens full-screen after install, works offline

6. Limitations (v1.0)

- No cloud backup — data only on one phone
- No multi-staff login / PIN
- No profit calculation (cost price not yet tracked)
- No barcode scanning
- No WhatsApp receipt sharing (download only)
- No admin dashboard to track users/installs
- No Play Store version yet (PWA only)

7. Roadmap — Next Features Discussed

- *A) Profit Tracking:* Add cost price, show daily profit
- *B) Staff PIN:* Owner PIN vs Sales Girl PIN, hide profit from staff
- *C) WhatsApp Receipt:* Send receipt image directly to customer on WhatsApp
- *D) Cloud Sync / Backup:* Supabase backup so data is not lost
- *E) Play Store Publish:* Wrap PWA via PWABuilder to .aab for Google Play

8. How to Use (For Shop Owners)

1. Open https://myshop-orcin-eta.vercel.app/
2. On Android: Menu > Add to Home Screen > Install
3. On iPhone: Share > Add to Home Screen
4. Go to Settings > Enter Shop Name
5. Go to Items > Add your products
6. Go to Sell > Start selling

---

Want me to make this into a clean PDF / Word-style version you can download and send?

Say *"make PDF"* and I'll generate it for you.
