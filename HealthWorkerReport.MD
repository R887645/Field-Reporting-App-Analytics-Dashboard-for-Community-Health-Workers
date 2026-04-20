# 📱 Digital Health Reporting App for Community Health Workers in Nigeria  
**Built with Power Apps, Dataverse & Power BI**  
*A step‑by‑step walkthrough of my Microsoft Elevate AI Developers Program Capstone Project*

---

## 🚨 Problem Statement  
Community Health Workers (CHWs) in rural Nigeria rely on paper forms to record patient visits. These forms are later re‑entered manually at Local Government Area (LGA) offices, often days later, leading to delays, errors, and data loss. Supervisors cannot act on health trends quickly enough, leaving communities underserved.  

---

## 🎯 Project Goal  
The goal of this app is to eliminate paper‑based reporting by enabling CHWs to record patient visits digitally on their phones. Data is stored directly in **Dataverse** and visualized in **Power BI**, giving supervisors real‑time insights into visit volumes, health trends, and community outreach coverage.  

---

## 🛠 Tools & Technologies  
- **Microsoft Power Apps** – Mobile data entry app  
- **Microsoft Dataverse** – Cloud data storage  
- **Microsoft Power BI Desktop** – Supervisor dashboard  
- **DAX & Power Query** – Data modelling and measures  
- **Microsoft 365 Developer Tenant** – Free sandbox environment  

---

## 📝 Step‑by‑Step Build Process  

### Step 1 — Designing the Data Model in Dataverse  
- Referenced **NPHCDA HMIS standard fields** to ensure real‑world relevance.  
- Created a `Patient_Information` table with required fields:  
  - Patient Full Name  
  - Visit ID  
  - Diagnosis  
  - Chief Complaint  
  - Patient Age  
  - Gender (Choice field)  
  - Community  
  - Local Government Area (LGA)  
  - Referral Needed (Yes/No)  
  - Visit Date  
- **Design decision:** Referral Needed and Gender as choice fields for cleaner Power BI filtering.  

*(Insert screenshot of Dataverse table here)*  

---

### Step 2 — Building the Power App  
- Built a **Canvas App** with two screens:  
  - **Screen 1:** Patient Visit Form with required fields and validation.  
  - **Screen 2:** Gallery of recent submissions with search and edit functionality.  
- Required fields marked with an asterisk (*) to guide CHWs.  

*(Insert screenshot of Patient Visit Form here)*  
*(Insert screenshot of Gallery Screen here)*  

---

### Step 3 — Entering Test Records  
- Entered 7 test records through the app to validate the end‑to‑end pipeline.  
- Records represented different communities, LGAs, diagnoses, and referral outcomes.  

*(Insert screenshot of Dataverse table populated with test records here)*  

---

### Step 4 — Connecting Dataverse to Power BI  
- Imported the Dataverse table into Power BI Desktop:  
  - Get Data → Dataverse → Environment URL → Sign in → Select table → Import mode.  
- Ensured stable connections and verified data integrity.  

*(Insert screenshot of Power BI Navigator showing Dataverse table here)*  

---

### Step 5 — Data Modelling with a Calendar Table  
- Created a Calendar dimension table using:  

```DAX
Calendar = CALENDARAUTO()
