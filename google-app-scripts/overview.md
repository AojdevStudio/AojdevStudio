<!-- === WATCHER HEADER START === -->
<!-- File: google-app-scripts/overview.md -->
<!-- Managed by file watcher -->
<!-- === WATCHER HEADER END === -->
# Google Apps Scripts Overview

<p align="center">
  <img src="./logo.svg" alt="Unified Dental Scripts Logo" width="200" height="200">
</p>

This document provides a simple overview of all the automated tools (Google Apps Scripts) that help run our dental practices. Each script is designed to make specific tasks easier and more efficient.

## 🦷 Lab Case Management

### What it does
- Tracks all lab cases for both Baytown and Humble locations
- Organizes cases by their current status:
  - Completed Cases
  - Cases Needing Attention
  - Cases to Return
  - Cancelled Cases
  - Re-do Cases
  - Scheduled & Paid Cases
- Automatically updates when changes are made
- Shows insurance payment status for each case

### How it helps
- Prevents cases from getting lost or forgotten
- Makes it easy to see which cases need attention
- Keeps track of insurance payments
- Helps manage patient appointments for lab cases

## 📞 Recall System

### What it does
- Manages patient recall appointments for both locations
- Tracks different types of responses:
  - Scheduled Appointments
  - Do Not Call (DNC)
  - Callback Requests
  - Already Scheduled Patients
- Keeps a daily log of all recall activities
- Can process historical recall data (backlog)

### How it helps
- Keeps patient recall organized
- Makes sure no patient falls through the cracks
- Helps track which patients need follow-up
- Shows how effective our recall system is working

## 💰 Billing Management

### What it does
- Tracks insurance billing status
- Flags cases that need doctor attention
- Moves important discussions to a separate tracking sheet
- Works for both Baytown and Humble locations

### How it helps
- Makes sure billing issues get proper attention
- Keeps doctors informed of cases needing review
- Helps track and resolve billing problems
- Improves insurance payment tracking

## 📊 Metrics & Reports

### Data Syncs
- Automatically collects data from different locations
- Updates central spreadsheets for tracking
- Runs on a schedule (like every Thursday at 5 PM for Humble)

### Payroll Processing
- Helps calculate bi-weekly payroll
- Automatically transfers and processes production data
- Makes payroll calculations more accurate

### Front Desk End-of-Day
- Tracks daily front desk activities
- Helps with end-of-day reporting
- Keeps operations organized

## 📈 Production Data Sync

### Provider-Specific Scripts
We have automated sync scripts for each provider:

#### Dentists
- Dr. Kam's Production Sync
- Dr. Obi's Production Sync
- Dr. Chi's Production Sync

#### Hygienists
- Adriane's Production Sync
- Kia's Production Sync

### What these scripts do
- Automatically collect daily production numbers
- Track performance against monthly goals
- Combine data from both locations (Baytown & Humble)
- Generate unique IDs for each entry to prevent duplicates
- Keep a detailed log of all sync activities
- Handle errors and send notifications if something goes wrong

### How they help
- Keep production tracking accurate and up-to-date
- Save time by automating data collection
- Prevent duplicate entries
- Make it easy to see provider performance
- Help with payroll calculations
- Ensure no production data gets missed

## 🔄 How Often Things Update

- Lab Cases: Updates instantly when changes are made
- Recall System: Can be run anytime through the menu
- Billing: Updates automatically when status changes
- Metrics: 
  - Humble data syncs every Thursday at 5 PM
  - Payroll processes bi-weekly
  - Front desk reports daily
- Production Data:
  - Updates automatically when changes are made
  - Syncs to master sheet on a regular schedule
  - Can be manually synced if needed

## 🛠 Available Tools

Most scripts add a menu to the top of your spreadsheet where you can:
- Run updates manually if needed
- Process backlogs of data
- Generate special reports
- Verify everything is working correctly

## 🔒 Data Security

All scripts include:
- Unique ID tracking to prevent duplicates
- Error logging and notifications
- Data validation before saving
- Automatic backups through Google Sheets
- Protected sheets and ranges where needed

---

Remember: These scripts are here to make your job easier! If something doesn't seem to be working right, just let the tech team know. 
