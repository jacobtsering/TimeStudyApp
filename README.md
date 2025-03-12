# Time Study Application - Setup and Testing Guide

This guide will help you set up and test the Time Study Application on your local machine using Visual Studio Code (VSCode).

## Prerequisites

Before you begin, make sure you have the following installed on your computer:

1. **Visual Studio Code (VSCode)** - A code editor
   - Download from: https://code.visualstudio.com/

2. **Node.js** - The JavaScript runtime
   - Download from: https://nodejs.org/ (choose the LTS version)

3. **Git** - Version control system
   - Download from: https://git-scm.com/downloads

## Setup Instructions

### Step 1: Download the Project

1. Open VSCode
2. Press `Ctrl+Shift+P` (Windows/Linux) or `Cmd+Shift+P` (Mac) to open the command palette
3. Type "Git: Clone" and select it
4. In the repository URL field, paste the URL of the repository
5. Choose a folder on your computer where you want to save the project
6. Click "Clone"

### Step 2: Open the Project

1. Once cloning is complete, click "Open" when prompted to open the repository
2. If not prompted, go to File > Open Folder and select the folder you just cloned

### Step 3: Install Dependencies

1. In VSCode, click on Terminal > New Terminal to open a terminal window
2. In the terminal, type the following command and press Enter:
   ```
   npm install
   ```
3. Wait for the installation to complete (this might take a few minutes)

### Step 4: Set Up the Database

1. In the terminal, type the following command and press Enter:
   ```
   npx prisma db push
   ```
2. This will create the database structure

### Step 5: Create Test Data

1. In the terminal, type the following command and press Enter:
   ```
   node scripts/seed.js
   ```
2. This will create sample companies, users, and operations for testing

### Step 6: Start the Development Server

1. In the terminal, type the following command and press Enter:
   ```
   npm run dev
   ```
2. Wait until you see a message saying the application is running (usually at http://localhost:3000)

### Step 7: Access the Application

1. Open your web browser
2. Go to http://localhost:3000
3. You'll see the login page of the time study application

## Testing the Application

### Login Credentials

Use one of the following test credentials to log in:

- **Admin User**:
  - Badge ID: `ADMIN001`
  
- **Operator Users**:
  - Badge ID: `OP001`
  - Badge ID: `OP002`

### Testing Admin Features

After logging in as an admin (ADMIN001), you can:

1. **Manage Users**:
   - View all users
   - Create new users
   - Edit existing users
   - Delete users
   - Assign operation access to operators

2. **Manage Operations**:
   - View all operations
   - Import new operations from Excel files
   - Replace existing operations with updated Excel files
   - Export time study data to Excel

### Testing Operator Features

After logging in as an operator (OP001 or OP002), you can:

1. **Select Operations**:
   - View operations you have access to
   - Select an operation to perform a time study

2. **Perform Time Studies**:
   - View operation details (ID, description, standard time, tools, quality check)
   - Start timer by typing or scanning "start"
   - Stop timer by typing or scanning "end"
   - Progress through operation steps automatically

### Simulating Barcode Scanning

To simulate barcode scanning:
1. Type "start" in the input field and press Enter to start the timer
2. Type "end" in the input field and press Enter to stop the timer

## Stopping the Application

When you're done testing:

1. Go back to VSCode
2. In the terminal, press `Ctrl+C` to stop the server

## Troubleshooting

- **Installation Issues**: Make sure Node.js and Git are properly installed
- **Application Won't Start**: Check the terminal for error messages
- **Login Problems**: Ensure you ran the seed script to create test users
- **Database Issues**: Try deleting the `prisma/dev.db` file and running `npx prisma db push` and `node scripts/seed.js` again

## Sample Data

The seed script creates:

- 1 company: "Test Manufacturing Inc."
- 1 admin user: "Admin User" (ADMIN001)
- 2 operator users: "Operator One" (OP001) and "Operator Two" (OP002)
- 2 processes: "LED Coin Circuit Assembly" and "Cylinder Lantern Assembly"
- 5 operations for each process
- Access permissions for operators to processes
