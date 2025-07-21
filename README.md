# 📦 UiPath Bot – Identification Bot
## Stack: UiPath, .Net, SQL, HTML, XML, LINQ, API, GitHub

This project demonstrates an enterprise-grade UiPath automation built using a custom UiPath process which has a stage like structure and used for bot that runs for several hours. The bot extracts, validates, and logs invoice data from a specified input folder, simulates a line-item matching process, and logs the results into a transaction log. Process 360,000–500,000 bankruptcy cases annually, boosting settlement amounts for a 150% ROI growth post-implementation. Undertook system upgrades and production support for 20 upgrades and functions improving processing timelines by 30% and generate over 30 million dollars in revenue for clients per year.

---

## 📁 Project Structure

This project follows the following structure:

```
📂 InvoiceProcessor_REFramework/
├── Framework/
│   ├── GetAppCredentials.xaml
│   ├── InitAllApplications.xaml
│   └── InitAllSettings.xaml
├── Data/
│   ├── Config.xlsx
│   └── InputInvoices/
├── Process/
│   └── Process.xaml
├── Main.xaml
├── Project.json
└── README.md
```

---

## 🔧 Configuration
All configuration values are stored in `Data/Config.xlsx`, including:
- Input/Output folder paths
- Exception handling settings
- Application credentials (via Orchestrator Assets)

---

## 🔄 Workflow Overview

### 1. **Init State**
- Reads config file and initializes applications (if needed)
- Retrieves credentials from Orchestrator

### 2. **PACER**
- Scans `InputInvoices/` directory for `.pdf` or `.xlsx` files
- Loads filenames into the transaction queue

### 3. **BCRS**
- Extracts invoice data using Regex and/or Excel activities
- Performs a dummy line-item match (simulate business logic)
- Logs results to output or Transaction Log sheet

### 4. **PECOS**
- Closes applications and performs clean-up

---
### 4. **BCRS**

## 📊 Logs & Exception Handling

- Transaction-level exceptions are handled using the built-in `SetTransactionStatus.xaml`
- Business and system exceptions are logged to Orchestrator
- Uses Retry mechanism for system exceptions as defined in Config

---

## 🧪 Testing

Use the sample files provided in `Data/InputInvoices/` to test various scenarios:
- Valid invoice
- Invalid format
- Missing data

---

## 📦 Dependencies

- UiPath.System.Activities
- UiPath.Excel.Activities
- UiPath.Mail.Activities (optional)

---
## 📝 Notes

This bot is designed to be modular and scalable. It can be extended to support:
- Integration with ERP systems (via API)
- OCR-based invoice processing
- Queue-based dispatch/performer model

---

## 📬 Contact

For questions or code access, please contact:  
📧 terrylamcao@gmail.com  
🔗 [LinkedIn](https://linkedin.com/in/terrylamcao)
