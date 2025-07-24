# 📦 UiPath Bot – Identification Bot
## Stack: UiPath, .Net, SQL, HTML, XML, LINQ, API, GitHub

This project demonstrates an enterprise-grade UiPath automation built using a custom UiPath process which has a stage like structure and used for bot that runs for 10 - 15 hours. 

The purpose to identify a larger percentage of bankruptcies that concern CMS in a timelier manner in order to drive higher ROI from the bankruptcy analysis process. Additionally, automating this process saves time that would otherwise be spent on manually searching PACER for bankruptcy cases. This will enable CMS personnel to more aggressively pursue recovery in the Chapter 7,11,13 reorganization (amongst other case types), and/or ensure safe transition of patient care. Medicare’s status as an unsecured creditor in bankruptcy necessitates proactive steps to safeguard trust funds. Automating the discovery of bankruptcy cases is the first step to proactively ensuring Medicare interests.

Process 360,000–500,000 bankruptcy cases annually, boosting settlement amounts for a 150% ROI growth post-implementation. Undertook system upgrades and production support for 20 upgrades and functions improving processing timelines by 30% and generate over 30 million dollars in revenue for clients per year.

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
│   ├── BCRS_Main.xaml
│   ├── BCRS_DataScraping.xaml
│   ├── BCRS_GetHICN.xaml
│   ├── BCRS_CheckSingleOrMultipleCase.xaml
│   └── BCRS_ProcessHICN.xaml
├── BOX/
│   ├── Box_AnalyticsReport.xaml
│   ├── Box_Archive.xaml
│   ├── Box_Login.xaml
│   └── Box_MainProcess.xaml
├── Finalize
│   ├── AnalyticReport.xaml
│   ├── Clean_MainProcess.xaml
│   └── SendEmails.xaml
├── Initialize
│   ├── Config_Setup.xaml
│   ├── Enterprise_Portal_Login.xaml
│   ├── Initialize_Settings_Apps.xaml
│   ├── LogInProcess.xaml
│   └── MFA.xaml
├── MIS
│   └── MIS_MainProcess.xaml
├── PACER
│   ├── Docket_MainProcess.xaml
│   ├── Pacer_BuildingMainTable.xaml
│   ├── Pacer_DataExtraction.xaml
│   ├── Pacer_Login.xaml
│   ├── Pacer_NavigateToQueue.xaml
│   ├── Pacer_QueueIllegalCharacterRemoval.xaml
│   ├── Pacer_QueueRetrieval.xaml
│   └── Pacer_Retrieval.xaml
├── PECOS
│   └── PECOS.xaml
│   └── PECOS_ProcessEIN.xaml
├── Process
│   └── TakeScreenshot.xaml
│   └── StageConfirmation.xaml
└── Main.xaml
└── Project.json


---

## 🔧 Configuration
All configuration values are stored in `Data/Config.xlsx`, including:
- Input/Output folder paths
- Exception handling settings
- Application credentials 

## 🔄 Workflow Overview

### 1. **Init State**
- Reads config file and initializes applications

### 2. **PACER**
- Bot navigates and log in PACER, do PACER searches
- Updates the Active Config File with the PACER status variables. 

### 3. **BCRS**
- Navigates BCRS webpage and verify if the case’s debtor (Individual) is found on it.
- Updates Bankruptcy report with findings.
- Updates the Active Config File with the BCRS status variables. 

### 4. **PECOS**
- Navigates PECOS webpage and verify if the case’s debtor (Corporation) is found on it.
- Updates Bankruptcy report with findings.
- Updates the Active Config File with the PECOS status variables. 

---
### 5 **DOCKET Download**
- Navigates PECOS webpage and verify if the case’s debtor (Corporation) is found on it.

### 6. **MIS**
- Navigates PECOS webpage and verify if the case’s debtor (Corporation) is found on it.
- Updates Bankruptcy report with findings.
- Updates the Active Config File with the PECOS status variables.

### 7. **Analytic Report**
- Navigates PECOS webpage and verify if the case’s debtor (Corporation) is found on it.
- Updates Bankruptcy report with findings.
- Updates the Active Config File with the PECOS status variables.

### 8. **Send Emails**
- Navigates PECOS webpage and verify if the case’s debtor (Corporation) is found on it.
- Updates Bankruptcy report with findings.
- Updates the Active Config File with the PECOS status variables.

### 8. **Cleap Up process**
- Navigates PECOS webpage and verify if the case’s debtor (Corporation) is found on it.
- Updates Bankruptcy report with findings.
- Updates the Active Config File with the PECOS status variables.

## 📊 Logs & Exception Handling
- Business and system exceptions are logged to local folder.
- Log is customized per individual xaml.
- Uses Retry mechanism for system exceptions as defined in Config.

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
This bot is designed to be modular and scalable.

## 📬 Contact
For questions or code access, please contact:  
📧 terrylamcao@gmail.com  
🔗 [LinkedIn](https://linkedin.com/in/terrylamcao)
