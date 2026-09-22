# Retail Feedback & Loyalty Management System

## Salesforce Retail Feedback & Loyalty Management System

A Salesforce-based **Retail Feedback & Loyalty Management System** designed to collect customer feedback, automatically award loyalty points, manage reward redemptions, and provide insights through Reports and Dashboards.

---

## Project Overview

This project provides a Salesforce solution for managing customer feedback and loyalty programs in retail businesses such as fashion, grocery, electronics, and other customer-facing stores.

The system helps manage:

- Customers
- Customer Feedback
- Loyalty Points
- Rewards
- Reward Redemptions
- Feedback Ratings
- Loyalty Tiers
- Customer Experience Analytics

---

## Technologies Used

- Salesforce
- Apex
- Lightning Web Components (LWC)
- SOQL
- Salesforce Flow
- Apex Triggers
- Custom Objects
- Salesforce Reports & Dashboards
- Lightning UI Record API

---

## Key Features

### 1. Customer Management

Manage customer information including contact details, store information, loyalty tier, and total loyalty points.

---

### 2. Feedback Management

Customers can submit feedback related to products, services, staff, stores, and delivery.

The system stores:

- Customer
- Product
- Store
- Rating
- Feedback Type
- Comments
- Feedback Date

---

### 3. Automatic Loyalty Points

An **Apex Trigger** automatically processes newly created feedback and calls the `FeedbackLoyaltyService` Apex class.

Loyalty points are awarded based on the customer's feedback rating.

| Rating | Loyalty Points |
|--------|----------------|
| 5      | 20             |
| 4      | 15             |
| 3      | 10             |
| 2      | 5              |
| 1      | 5              |

---

### 4. Points Tracking

The **Points Tracker LWC** allows users to select a customer and view their total loyalty points.

---

### 5. Rewards Catalog

The **Rewards Catalog LWC** displays available rewards and the points required to redeem them.

Example rewards:

- ₹50 Discount — 100 Points
- ₹100 Discount — 200 Points
- Free Product — 300 Points
- Premium Reward — 500 Points

---

### 6. Reward Redemption

A **Salesforce Screen Flow** is used to manage the reward redemption process.

The Flow:

1. Selects Customer
2. Selects Reward
3. Accepts Points Used
4. Checks Available Points
5. Creates Redemption Record
6. Updates Customer Points
7. Displays Success/Error Message

---

### 7. LWC → Flow Integration

The **Rewards Catalog LWC** launches the **Redeem Reward Flow** when the user clicks the **Redeem Reward** button.

```text
Rewards Catalog LWC
        ↓
   Redeem Reward
        ↓
Redeem Reward Flow
        ↓
Check Available Points
        ↓
Create Redemption
        ↓
Update Customer
        ↓
Success / Error
