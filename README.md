# SecurePay — UPI Fraud Awareness & Budget Manager

SecurePay is an interactive web-based financial safety and budgeting tool designed to help users understand common UPI fraud techniques, manage personal spending, follow the 50-30-20 budgeting rule, set category-wise spending limits, and evaluate the risk of a transaction before making a payment.

The project combines **UPI fraud awareness, personal finance management, spending analytics, budget monitoring, and pre-transaction risk analysis** into a single responsive interface. :chatgpt-content-reference{index="0"}

---

## Project Overview

Digital payments through UPI have made transactions fast and convenient, but they also introduce various security risks. SecurePay provides an educational and interactive environment where users can learn about common fraud patterns while also maintaining better control over their spending.

The application is divided into five major sections:

- UPI Fraud Awareness
- 50-30-20 Budget Calculator
- UPI Spending Tracker
- Smart Budget Limits
- Pre-Transaction Risk Analyzer

The application also includes a security checklist that allows users to track important UPI safety practices. :chatgpt-content-reference{index="1"}

---

## Key Features

### 1. UPI Fraud Awareness

The fraud awareness section explains common UPI fraud techniques and provides prevention tips for each one.

The application covers:

- Phishing Links
- Fake Customer Care
- QR Code Scams
- UPI Collect Request Fraud
- SIM Swap Attacks
- Malicious Applications

Each fraud type includes:

- Fraud category
- Description
- Risk classification
- Prevention advice

For example, the QR Code Scam section explains the risk of mistakenly approving a payment while believing that a QR code is being used to receive money. :chatgpt-content-reference{index="2"}

### Security Checklist

SecurePay provides an interactive checklist containing important UPI security practices.

Users can mark practices as completed, such as:

- Never sharing a UPI PIN
- Verifying the recipient before payment
- Avoiding suspicious payment links
- Checking collect requests
- Enabling application locks
- Reporting suspicious UPI IDs
- Checking transaction history
- Never entering a PIN to receive money

Checklist progress is stored locally in the browser. :chatgpt-content-reference{index="3"}

---

## 2. 50-30-20 Budget Calculator

The application implements the **50-30-20 budgeting rule**.

Users enter their monthly income, and the application automatically calculates:

| Category | Allocation | Purpose |
|---|---:|---|
| Needs | 50% | Essential expenses |
| Wants | 30% | Discretionary spending |
| Savings | 20% | Savings and investments |

For example, with a monthly income of ₹50,000:

- Needs = ₹25,000
- Wants = ₹15,000
- Savings = ₹10,000

The results are displayed through interactive cards and a visual budget chart. :chatgpt-content-reference{index="4"}

### Spending Categories

The application provides guidance for categorizing expenses such as:

- Food
- Transport
- Shopping
- Utilities
- Entertainment
- Healthcare

Some expenses can belong to different categories depending on their purpose. For example, groceries may be considered a need while dining out may be considered a want. :chatgpt-content-reference{index="5"}

---

## 3. UPI Spending Tracker

The spending tracker allows users to manually record their transactions.

Each transaction can contain:

- Amount
- Category
- 50-30-20 bucket
- Merchant / UPI ID
- Transaction date

Available categories include:

- Food & Dining
- Transport
- Shopping
- Utilities & Bills
- Entertainment
- Health & Medical
- Education
- Savings / Investment
- Others

Users can add and delete transactions from the tracker. :chatgpt-content-reference{index="6"}

### Spending Statistics

The dashboard calculates:

- Total Spent
- Needs Spending
- Wants Spending
- Savings Spending

The application also generates a category-based spending chart to visually represent how money is distributed across different expense categories.

---

## 4. Smart Budget Limits

SecurePay allows users to establish monthly spending limits for different categories.

Default limits are provided for categories such as:

- Food
- Transport
- Shopping
- Utilities
- Entertainment
- Health
- Education
- Others

The application compares the amount spent against the configured limit and displays a progress bar.

The progress status changes depending on usage:

- Safe: Below 70%
- Warning: 70%–89%
- Danger: 90% or above

When spending reaches a critical level, the application displays a budget alert. :chatgpt-content-reference{index="7"}

Users can also update individual category limits.

---

## 5. Pre-Transaction Risk Analyzer

The Pre-Transaction Risk Analyzer is one of the main security features of SecurePay.

Before making a payment, users can enter transaction information such as:

- Transaction amount
- Recipient type
- Transaction time
- Device being used
- Transaction context

Recipient types include:

- Known Contact
- New UPI ID / Unknown
- Suspicious / Random ID

Transaction contexts include:

- Regular Purchase / Transfer
- Urgent / Pressure to Pay
- Prize / Cashback / Reward Claim
- KYC / Account Update Request

The analyzer evaluates these factors and generates a risk score. :chatgpt-content-reference{index="8"}

---

## Risk Scoring System

The risk analyzer uses a rule-based scoring system.

### Transaction Amount

| Amount | Risk Points |
|---|---:|
| Up to ₹10,000 | +0 |
| ₹10,001–₹20,000 | +8 |
| ₹20,001–₹50,000 | +15 |
| Above ₹50,000 | +25 |

### Recipient

| Recipient | Risk Points |
|---|---:|
| Known recipient | +0 |
| New recipient | +15 |
| Suspicious recipient | +25 |

### Transaction Time

| Time | Risk Points |
|---|---:|
| Normal hours | +0 |
| Late night | +8 |
| Very unusual time | +15 |

### Device

| Device | Risk Points |
|---|---:|
| Known device | +0 |
| New device | +8 |
| Public/shared device | +15 |

### Transaction Context

| Context | Risk Points |
|---|---:|
| Normal transaction | +0 |
| Urgent/pressure payment | +12 |
| Reward/prize pattern | +20 |
| KYC/account update pattern | +20 |

The final score is capped at 100. :chatgpt-content-reference{index="9"}

### Risk Levels

The resulting score is classified into three levels:

**Low Risk**

Score below 40.

The application indicates that the transaction falls within its defined normal parameters while still recommending recipient verification.

**Moderate Risk**

Score from 40 to 69.

The application identifies unusual characteristics and recommends checking the recipient and transaction purpose.

**High Risk**

Score of 70 or above.

The application identifies multiple fraud indicators and recommends cancelling or independently verifying the recipient before proceeding.

These classifications are implemented through JavaScript rules rather than machine-learning predictions. :chatgpt-content-reference{index="10"}

---

## Technology Stack

### Frontend

- HTML5
- CSS3
- JavaScript
- HTML Canvas API

### Styling

The application uses a custom dark-themed interface with:

- CSS variables
- Responsive grids
- Cards
- Gradient elements
- Hover animations
- Progress bars
- Responsive media queries
- Toast notifications
- Smooth scrolling

The primary theme uses dark blue backgrounds with green accents and separate colors for warnings, errors, and information. :chatgpt-content-reference{index="11"}

### Data Storage

SecurePay uses the browser's **LocalStorage API** to persist:

- Transactions
- Budget limits
- Security checklist progress

No external database is required for the current implementation. :chatgpt-content-reference{index="12"}

---

## Application Architecture

The application follows a lightweight client-side architecture:

```text
User
  |
  v
SecurePay Web Interface
  |
  +----------------------+
  |                      |
  v                      v
Budget Management    Fraud Awareness
  |                      |
  +----------+-----------+
             |
             v
       JavaScript Logic
             |
     +-------+-------+
     |       |       |
     v       v       v
LocalStorage Charts Risk Engine
```

All major application logic runs in the browser.

---

## Data Flow

### Budget Calculator

```text
Monthly Income
      |
      v
50% Needs
30% Wants
20% Savings
      |
      v
Budget Chart + Result Cards
```

### Spending Tracker

```text
Transaction Input
      |
      v
Validation
      |
      v
Transaction Object
      |
      v
LocalStorage
      |
      +----> Transaction List
      |
      +----> Statistics
      |
      +----> Spending Chart
      |
      +----> Budget Limits
```

### Risk Analyzer

```text
Transaction Details
        |
        v
Amount Evaluation
        |
        +---- Recipient Evaluation
        |
        +---- Time Evaluation
        |
        +---- Device Evaluation
        |
        +---- Context Evaluation
        |
        v
Risk Score
        |
        v
Low / Moderate / High Risk
        |
        v
Recommended Action
```

---

## LocalStorage Implementation

SecurePay stores user data locally in the browser.

The application uses separate storage keys for different types of information:

```text
securepay_tx
securepay_limits
securepay_checklist
```

This allows the application to retain user-entered information even after refreshing the page.

Because the current implementation uses browser LocalStorage, the data is local to the browser and is not synchronized with an external account or database. :chatgpt-content-reference{index="13"}

---

## User Interface

The interface is designed around a modern dashboard-style layout.

### Navigation

The fixed navigation bar provides access to:

- Fraud Awareness
- 50-30-20 Rule
- Spending Tracker
- Budget Limits
- Risk Analyzer

The navigation remains visible while scrolling and highlights the active section. :chatgpt-content-reference{index="14"}

### Responsive Design

The application includes responsive CSS rules for smaller screens.

The layout adapts by:

- Hiding desktop navigation links on smaller screens
- Reducing hero heading size
- Converting multi-column result cards into single-column layouts
- Changing the spending tracker layout from two columns to one column

This allows the application to work across desktop and mobile screen sizes. :chatgpt-content-reference{index="15"} :chatgpt-content-reference{index="16"}

---

## Visualizations

SecurePay uses the HTML Canvas API for financial visualizations.

### Budget Chart

The budget chart visualizes:

- Needs
- Wants
- Savings

according to the 50-30-20 allocation. :chatgpt-content-reference{index="17"}

### Spending Chart

The spending chart dynamically calculates category totals and displays their relative distribution.

The chart also includes:

- Category percentages
- Category legend
- Total number of spending categories

The chart updates whenever transactions are added or deleted. :chatgpt-content-reference{index="18"}

---

## Validation and Notifications

The application performs basic input validation before processing user actions.

Examples include:

- Invalid transaction amounts
- Invalid budget limits
- Missing risk-analysis amounts

Users receive visual toast notifications when actions succeed or fail.

Examples include:

```text
Transaction added
Transaction deleted
Limit updated
Invalid amount
Security checklist updated
```

The notification system automatically removes messages after a short period. :chatgpt-content-reference{index="19"}

---

## Project Structure

A simple implementation can be organized as:

```text
SecurePay/
│
├── index.html
├── README.md
│
├── assets/
│   ├── images/
│   └── icons/
│
└── screenshots/
```

If the HTML, CSS, and JavaScript are kept in a single file, the project can also be structured as:

```text
SecurePay/
│
├── index.html
└── README.md
```

---

## How to Run the Project

### Option 1 — Open Directly

1. Clone or download the repository.
2. Open the project folder.
3. Open `index.html` in a modern web browser.
4. Start using SecurePay.

### Option 2 — VS Code Live Server

1. Open the project in Visual Studio Code.
2. Install the **Live Server** extension.
3. Right-click `index.html`.
4. Select **Open with Live Server**.
5. The application will open in your browser.

No backend server or database setup is required for the current implementation.

---

## Example Workflow

A typical user session can follow this process:

```text
1. Learn about common UPI frauds
              ↓
2. Complete the security checklist
              ↓
3. Enter monthly income
              ↓
4. Review 50-30-20 budget
              ↓
5. Record UPI transactions
              ↓
6. Monitor category spending
              ↓
7. Configure budget limits
              ↓
8. Check transaction risk before payment
```

---

## Educational Purpose

SecurePay is primarily an **educational and awareness project**.

It demonstrates how a client-side web application can combine:

- Financial planning
- Data visualization
- Local data storage
- Rule-based risk analysis
- Interactive UI components
- Digital payment security awareness

The project is not intended to replace a bank's fraud detection system or provide a guaranteed prediction of whether a transaction is fraudulent.

The application's own interface states that it is an educational tool and recommends contacting the bank and reporting incidents to the appropriate payment authorities in case of actual fraud. :chatgpt-content-reference{index="20"}

---

## Limitations

The current version has several technical limitations:

- It does not connect to a real UPI account.
- Transactions must be entered manually.
- It does not access live bank transaction data.
- Risk analysis is rule-based.
- It does not use machine learning.
- Data is stored only in browser LocalStorage.
- Clearing browser storage can remove saved application data.
- The risk score should not be interpreted as a guaranteed fraud prediction.
- There is no authentication system or multi-user database.

---

## Future Enhancements

Possible future improvements include:

- Backend API integration
- User authentication
- Cloud database
- Secure user accounts
- Real-time transaction monitoring
- Machine-learning-based fraud detection
- Anomaly detection
- Transaction history import
- Monthly financial reports
- PDF report generation
- Advanced spending analytics
- Budget recommendations
- Notification system
- Mobile application
- Integration with official payment and banking services
- Improved accessibility
- Multi-language support

---

## Learning Outcomes

This project demonstrates practical implementation of several web-development and software concepts:

- HTML structure and semantic organization
- CSS variables and responsive design
- JavaScript DOM manipulation
- Event handling
- Form validation
- Arrays and objects
- Array filtering and aggregation
- LocalStorage
- Dynamic HTML rendering
- Canvas-based data visualization
- Rule-based decision systems
- Responsive UI design
- Client-side application architecture

---

## Security Awareness

The project emphasizes several important principles for safer digital payments:

```text
Never share your UPI PIN
        ↓
Verify the recipient
        ↓
Be careful with QR codes
        ↓
Reject suspicious collect requests
        ↓
Avoid unknown payment links
        ↓
Be cautious of urgent payment requests
        ↓
Verify unusual KYC/reward requests
```

The application is designed to encourage users to pause and verify transaction details before completing a payment.

---

## Conclusion

SecurePay brings **UPI fraud awareness and personal financial management into one interactive web application**.

Instead of focusing only on fraud awareness or only on budgeting, the project combines both areas:

```text
Fraud Awareness
       +
Budget Planning
       +
Expense Tracking
       +
Budget Monitoring
       +
Risk Analysis
       =
SecurePay
```

The project demonstrates how a lightweight frontend application can provide useful educational tools without requiring a backend database or external financial service.

**SecurePay — Secure Your UPI. Master Your Money.**
