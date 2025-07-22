# 📦 UiPath Bot – Identification Bot
## Stack: UiPath, .Net, SQL, HTML, XML, LINQ, API, GitHub

This project demonstrates an enterprise-grade UiPath automation built using a custom UiPath process which has a stage like structure and used for bot that runs for several hours. The bot extracts, validates, and logs invoice data from a specified input folder, simulates a line-item matching process, and logs the results into a transaction log. Process 360,000–500,000 bankruptcy cases annually, boosting settlement amounts for a 150% ROI growth post-implementation. Undertook system upgrades and production support for 20 upgrades and functions improving processing timelines by 30% and generate over 30 million dollars in revenue for clients per year.

---

## 📁 Project Structure

This project follows the following structure:

```
📂 Bankruptcy_Identification/
├── Data/
│   ├── Analytics.csv
│   ├── BankruptcyReport.xlsx
│   ├── ChaptersQueue.xlsx
│   ├── BankruptcyReport.xlsx
│   ├── Config.xlsx
│   ├── CourtCrosswalk.xlsx
│   └── Emails.xlsx
├── BCRS/
│   ├── Config.xlsx
│   └── InputInvoices/
├── BOX/
│   └── Process.xaml
├── Finalize
│   └── Process.xaml
│   └── Process.xaml
│   └── Process.xaml
├── Initialize
│   └── Process.xaml
│   └── Process.xaml
│   └── Process.xaml
├── MIS
│   └── Process.xaml
│   └── Process.xaml
│   └── Process.xaml
├── PACER
│   └── Process.xaml
│   └── Process.xaml
│   └── Process.xaml
├── PECOS
│   └── Process.xaml
│   └── Process.xaml
│   └── Process.xaml
├── Process
│   └── Process.xaml
│   └── Process.xaml
│   └── Process.xaml
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
- UiPath.Database.Activities - v1.7.1
- UiPath.Credentials.Activities - v2.0.0 
- UiPath.PDF.Activities - v3.10.1
- UiPath.Mail.Activities - v1.12.3
- UiPath.WebAPI.Activities - v2.20.2
- UiPath.UiAutomation.Activities - v22.10.4
- UiPath.System.Activities - v22.10.5
- Microsoft 365 - v2.2.4

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
