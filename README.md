Retail Feedback & Loyalty Management System

svg

Salesforce Retail Feedback & Loyalty Management System

svg

A Salesforce-based Retail Feedback & Loyalty Management System designed to collect customer feedback, automatically award loyalty points, manage reward redemptions, and provide insights through Reports and Dashboards.

Project Overview

svg

This project provides a Salesforce solution for managing customer feedback and loyalty programs in retail businesses such as fashion, grocery, electronics, and other customer-facing stores.

The system helps manage:

Customers
Customer Feedback
Loyalty Points
Rewards
Reward Redemptions
Feedback Ratings
Loyalty Tiers
Customer Experience Analytics
Technologies Used

svg

Salesforce
Apex
Lightning Web Components (LWC)
SOQL
Salesforce Flow
Apex Triggers
Custom Objects
Salesforce Reports & Dashboards
Lightning UI Record API
Key Features

svg

1. Customer Management

svg

Manage customer information including contact details, store information, loyalty tier, and total loyalty points.

2. Feedback Management

svg

Customers can submit feedback related to products, services, staff, stores, and delivery.

The system stores:

Customer
Product
Store
Rating
Feedback Type
Comments
Feedback Date
3. Automatic Loyalty Points

svg

An Apex Trigger automatically processes newly created feedback and calls the FeedbackLoyaltyService Apex class.

Loyalty points are awarded based on the customer's feedback rating.

Example:

Rating	Points
5	20
4	15
3	10
2	5
1	5
4. Points Tracking

svg

The Points Tracker LWC allows users to select a customer and view their total loyalty points.

5. Rewards Catalog

svg

The Rewards Catalog LWC displays available rewards and the points required to redeem them.

Example rewards:

₹50 Discount
₹100 Discount
Free Product
Premium Reward
6. Reward Redemption

svg

A Salesforce Screen Flow is used to manage the reward redemption process.

The Flow:

Selects Customer
Selects Reward
Accepts Points Used
Checks Available Points
Creates Redemption Record
Updates Customer Points
Displays Success/Error message
7. LWC → Flow Integration

svg

The Rewards Catalog LWC launches the Redeem Reward Flow when the user clicks the Redeem Reward button.

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
8. Reports & Dashboards

svg

Salesforce Reports and Dashboards are used to analyze:

Feedback by Product
Feedback by Store
Average Feedback Rating
Customer Loyalty
Top Redeemed Rewards
Total Feedback
Loyalty Distribution
Salesforce Development Concepts

svg

Apex Classes
Apex Triggers
SOQL
LWC
Salesforce Flow
LWC → Flow Integration
Lightning UI Record API
Custom Objects
Lookup Relationships
Data Modeling
Automation
Reports & Dashboards
Salesforce Security & Validation
Apex Components

svg

Apex Class
FeedbackLoyaltyService.cls

Responsible for calculating loyalty points based on feedback rating and creating Loyalty_Point__c records.

Apex Trigger
FeedbackTrigger.trigger

Runs after a new Feedback__c record is created and calls the FeedbackLoyaltyService class.

Lightning Web Components

svg

1. Submit Feedback
submitFeedback
├── submitFeedback.html
├── submitFeedback.js
└── submitFeedback.js-meta.xml

Used to submit customer feedback.

2. Points Tracker
pointsTracker
├── pointsTracker.html
├── pointsTracker.js
└── pointsTracker.js-meta.xml

Used to display customer loyalty points.

3. Rewards Catalog
rewardsCatalog
├── rewardsCatalog.html
├── rewardsCatalog.js
└── rewardsCatalog.js-meta.xml

Used to display rewards and launch the redemption Flow.

Salesforce Flow

svg

Redeem Reward Flow

Flow Type: Screen Flow

API Name:

Redeem_Reward_Flow

The Flow handles the complete reward redemption process including customer selection, points validation, redemption creation, and points deduction.

Project Structure

svg

force-app/
└── main/
    └── default/
        ├── classes/
        │   ├── FeedbackLoyaltyService.cls
        │   └── FeedbackLoyaltyService.cls-meta.xml
        │
        ├── triggers/
        │   ├── FeedbackTrigger.trigger
        │   └── FeedbackTrigger.trigger-meta.xml
        │
        ├── lwc/
        │   ├── submitFeedback/
        │   │   ├── submitFeedback.html
        │   │   ├── submitFeedback.js
        │   │   └── submitFeedback.js-meta.xml
        │   │
        │   ├── pointsTracker/
        │   │   ├── pointsTracker.html
        │   │   ├── pointsTracker.js
        │   │   └── pointsTracker.js-meta.xml
        │   │
        │   └── rewardsCatalog/
        │       ├── rewardsCatalog.html
        │       ├── rewardsCatalog.js
        │       └── rewardsCatalog.js-meta.xml
        │
        ├── objects/
        │   ├── Customer__c/
        │   ├── Feedback__c/
        │   ├── Loyalty_Point__c/
        │   └── Redemption__c/
        │
        └── flows/
            └── Redeem_Reward_Flow.flow-meta.xml
Project Architecture
                  Salesforce
                       │
        ┌──────────────┴──────────────┐
        │                             │
   Customer__c                    Feedback__c
        │                             │
        │                       FeedbackTrigger
        │                             │
        │                   FeedbackLoyaltyService
        │                             │
        │                       Loyalty_Point__c
        │
        ├──── Points Tracker LWC
        │
        └──── Rewards Catalog LWC
                       │
                       ↓
              Redeem Reward Flow
                       │
                       ↓
                Redemption__c
Conclusion

The Retail Feedback & Loyalty Management System demonstrates practical Salesforce development using Apex, Apex Triggers, Lightning Web Components, Salesforce Flow, Custom Objects, Automation, Reports, and Dashboards.
