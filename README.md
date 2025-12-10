# FULL PROJECT MILESTONE DOCUMENT

## E-Commerce / Restaurant Reservation App — Flutter + Firebase — Clean Code + SOLID

---

# **Milestone 0 — Project Setup & Standards (FOUNDATION)**  
### **Goal**
Create a reproducible development environment and enforce clean, maintainable code structure.

### **Deliverables**
- Flutter project initialized & pushed to Git.
- `analysis_options.yaml` with strict lint rules using `flutter_lints`.
- Basic CI config (GitHub Actions) to run:
  - `flutter analyze`
  - `flutter test`
- Clean Architecture folder structure.
- Updated `pubspec.yaml` with required dependencies.
- Firebase project created and `google-services.json` added.
- README with:
  - Setup instructions  
  - Firebase configuration checklist  
  - Emulator setup  

### **Acceptance Criteria**
- `flutter analyze` passes without critical warnings.
- `flutter run` launches successfully.
- Firebase initializes without runtime errors.
- Developer can follow README to recreate environment.

### **Branch:** `chore/init`

---

# **Milestone 1 — Domain & Firestore Schema Design**
### **Goal**
Define domain models & Firestore structure before coding features.

### **Deliverables**
- Domain entities (Freezed-based):
  - `User`, `Category`, `Restaurant`, `Table`, `TimeSlot`, `Booking`
- Firestore Schema Document with:
  - Collection structure  
  - Sample JSON documents  
  - Required indexes  
- Deterministic slot ID scheme:
  ```
  restaurantId_YYYYMMDD_slotIndex_tableId
  ```
- Freezed + JSON mapping models.
- Firestore sample seed data.

### **Acceptance Criteria**
- All entities compile using code generation.
- Schema document is complete and approved.
- Serialization/deserialization works correctly.

### **Branch:** `feat/schema`

---

# **Milestone 2 — Authentication & User Management**
### **Goal**
Implement customer authentication and user profile persistence.

### **Deliverables**
- Register screen (email/password).
- Login screen with validation.
- Riverpod AuthState provider.
- Firestore `/users/{uid}` creation and updates.
- Route protection & redirects.

### **Acceptance Criteria**
- Users can register and sign in.
- User profile is created automatically.
- Unauthorized users cannot access protected routes.

### **Branch:** `feat/auth`

---

# **Milestone 3 — Vendor App: CRUD for Restaurants**
### **Goal**
Enable vendor to add and manage restaurant data and view bookings.

### **Deliverables**
- Vendor app skeleton (separate flavor or target).
- Add Restaurant Screen:
  - Name  
  - Description  
  - Category  
  - Tables count  
  - Image upload (Firebase Storage)  
  - Location capture  
- Restaurant List & Edit Screens.
- Real-time bookings view for vendor.

### **Acceptance Criteria**
- Restaurants stored correctly in Firestore.
- Image uploads return valid URLs.
- Vendor receives real-time booking updates.

### **Branch:** `feat/vendor-crud`

---

# **Milestone 4 — Customer App: Browse & Details**
### **Goal**
Enable customers to browse categories, search restaurants, and view details.

### **Deliverables**
- Category screen.
- Restaurants list with pagination.
- Search (by name).
- Restaurant details:
  - Images  
  - Description  
  - Tables  
  - Time Slots  
- Firestore offline persistence enabled.

### **Acceptance Criteria**
- Search works correctly.
- Pagination is stable.
- All details load without errors.

### **Branch:** `feat/customer-browse`

---

# **Milestone 5 — Booking Flow with Atomic Transactions**
### **Goal**
Implement safe, concurrency-proof booking flow.

### **Deliverables**
- Booking screen with:
  - Date picker  
  - Table selection  
  - Slot selection  
- Firestore `runTransaction` booking system.
- Atomic slot claiming using deterministic slot IDs.
- Cancel booking functionality.
- Concurrency tests (simulating two users).

### **Acceptance Criteria**
- Only one simultaneous booking succeeds.
- Other devices see updated availability instantly.
- Canceling a booking frees the slot.

### **Branch:** `feat/booking`

---

# **Milestone 6 — Notifications & Vendor Alerts**
### **Goal**
Notify vendor in real time when bookings occur.

### **Deliverables**
- Firebase Messaging integration.
- Save vendor device tokens.
- Cloud Function to send notification on booking creation.
- Vendor notification list.

### **Acceptance Criteria**
- Vendor receives push notification.
- Notification opens relevant booking details.

### **Branch:** `feat/notifications`

---

# **Milestone 7 — UI Polish, Themes, Accessibility**
### **Goal**
Improve UI quality and accessibility.

### **Deliverables**
- Global theme & design system.
- Light/Dark mode.
- Accessibility features.
- Animations for loading and booking success.

### **Acceptance Criteria**
- Visual consistency.
- Good contrast & large tap areas.
- Smooth animations.

### **Branch:** `chore/ui-polish`

---

# **Milestone 8 — Tests, Firestore Rules & CI**
### **Goal**
Add automated safety and validation.

### **Deliverables**
- Unit tests for domain logic.
- Widget tests for booking.
- Firestore rules.
- CI (lint, tests, build_runner).

### **Acceptance Criteria**
- All tests pass.
- Rules validated via Firebase Emulator.

### **Branch:** `chore/tests-ci`

---

# **Milestone 9 — Release & Documentation**
### **Goal**
Package the project for final delivery.

### **Deliverables**
- Final README.
- Architecture document.
- Demo video or screenshots.
- APK or AAB build.

### **Acceptance Criteria**
- Reviewer can run the app easily.
- All workflows fully functional.

### **Branch:** `release/v1.0`

---

# **MVP Path**
The minimum needed to deliver a functional college-grade system:

1. Milestone 0  
2. Milestone 1  
3. Milestone 2  
4. Milestone 4  
5. Milestone 5  
6. Basic Milestone 3 (Vendor add restaurant)

---

