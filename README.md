# smart-POS
This is a desktop-based sales management application built using Visual Basic .NET in Visual Studio 2022. The app connects to a local MySQL database via an ODBC connection. It is designed to handle basic sales transactions and product management with a clean and simple interface.

## Features

### 1. Sales Transactions
- Accessible via Form1
- Auto-generated sales invoice number (read-only)
- Allows users to:
  - Select a transaction date using a `DateTimePicker`
  - Choose a customer from a dropdown (automatically fills in related details)
  - Add products to a transaction via dropdown (auto-fills code, category, price, etc.)
  - Enter quantity to calculate subtotal automatically
- Sales data is added to the transaction log after pressing the **Add** button
- Total sales amount is only saved to the database when the **Save** button is clicked
- Added items are displayed in a `DataGridView` with a live total calculator

### 2. Product Management
- Accessible via Form2
- Two main sections:
  - Add Product Categories & Units
    - Input category or unit using text fields and save them with action buttons
  - Add New Products
    - Auto-generated product codes (read-only)
    - Input fields for product name, category, unit, purchase price, selling price, and initial stock
    - Data saved to the product table upon clicking Save Product

### Input Validation
- Input fields use `ErrorProvider` for error handling and validation
- Users are prevented from submitting empty or invalid data

---

## How to Run the App

1. Open the project in Visual Studio 2022.
2. Make sure XAMPP (or your local MySQL server) is running.
3. Import the .sql file included in this repository into your MySQL database via phpMyAdmin:
   - Login to phpMyAdmin.
   - Create a new database (if needed).
   - Go to the Import tab and upload the `.sql` file from this repo.
   - Execute the import to create all tables and initial data.
4. Set up an ODBC connection to link your database:
   - Open ODBC Data Source Administrator on your PC.
   - Create a new System DSN.
   - Select the MySQL ODBC driver.
   - Enter the server, port, database name, username, and password.
   - Use this DSN name (e.g., `koneksi_dblatihan2`) in the app’s connection string.
5. Run the application through Visual Studio.
6. Use the MenuStrip to switch between the Transaction Form and Product Management Form.

---

