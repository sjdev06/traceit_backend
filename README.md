 Initial Setup & Core Features
1️⃣ Project Setup
Tech Stack:

Backend: Node.js, Express.js

Database: Firebase Firestore

Testing: Manual testing with assert (no Jest)

Design Decisions:

Used Firebase Firestore instead of SQL for flexible, scalable storage.

Kept APIs RESTful with clear separation of concerns (services, controllers).

🚀 Phase 1: Core Functionalities
2️⃣ Lost & Found Service (lostFoundService.js)
APIs Implemented:

createItem(): Add lost/found items.

getAllItems(): Retrieve all lost/found items.

getItemById(): Fetch details of a single item.

resolveItem(): Mark item as resolved.

deleteItem(): Remove an item.

Firestore Integration:

Used collection(db, "lost_found") for CRUD operations.

Added serverTimestamp for tracking item posting time.

3️⃣ Sell & Donate Service (sellDonateService.js)
APIs Implemented:

createSellItem(): Add items for sale/donation.

getAllSellItems(): Fetch all items for sale/donation.

markAsSold(): Mark an item as sold.

deleteSellItem(): Remove an item.

Firestore Integration:

Used collection(db, "sell_donate").

Ensured same CRUD structure as lostFoundService.js.

🔍 Phase 2: Enhancements & Testing
4️⃣ Search & Filtering Enhancements
Design Decisions:

Added support for category, location, date filtering.

Used Firestore where() and orderBy() queries.

Implementation:

Query parameters allow flexible filtering via API.

title & description enabled for text-based searching.

5️⃣ End-to-End Testing (testEndToEnd.js)
Test Scenarios Covered:

✅ Creating, fetching, resolving, and deleting Lost & Found items.

✅ Creating, fetching, marking as sold, and deleting Sell/Donate items.

Design Decisions:

Used plain Node.js assertions (assert) instead of Jest.

Debugging with console.log() for real-time tracking.

Fixes & Improvements:

Added missing sellDonateService.js.

Ensured getItemById() properly checks doc.exists().

Handled "Cannot destructure property 'category' of 'undefined'" issue.

🛑 Deferred to Round 3
6️⃣ Email & Image Handling
Planned Features:

📧 Email Alerts: Notify users when a lost item is found.

📸 Image Uploads: Support Firebase Storage for item images.

Reason for Delay:

Focused on core functionality first before adding notifications/media.

✅ Current Status
Feature	Status
Lost & Found CRUD	✅ Done
Sell & Donate CRUD	✅ Done
Search & Filtering	✅ Done
End-to-End Testing	✅ Done
Email Notifications	⏳ Deferred to Round 3
Image Handling	⏳ Deferred to Round 3
