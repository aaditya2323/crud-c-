# CRUD Application using CGI in C++

This project is a simple CRUD (Create, Read, Update, Delete) application written in C++ using CGI (Common Gateway Interface). It allows users to add, update, and delete records (name, address, phone) through a web interface.

## Features
- **Add a Record**: Add new records with a name, address, and phone number.
- **Update a Record**: Update existing records by searching for the name and changing the address or phone number.
- **Delete a Record**: Delete a record based on the name.
- **File-based Data Storage**: Records are stored in a text file on the server.

## Project Structure
|-- cgi-bin/ |-- crud.cgi # Compiled CGI script (C++ executable) |-- records.txt # Data file where records are stored |-- html/ |-- index.html # Front-end HTML file for the CRUD application |-- src/ |-- crud.cpp # Source code of the CRUD application |-- README.md # Project documentation


## Prerequisites

To run this project, you'll need:
- A web server (e.g., Apache with CGI support).
- C++ compiler (e.g., `g++`).
- Basic knowledge of setting up a CGI script in the web server.

## How to Run the Project

### Step 1: Set up a Local Web Server
1. Install [XAMPP](https://www.apachefriends.org/index.html) (or any server with CGI support like Apache).
2. Configure your web server to allow CGI execution. For XAMPP, you need to ensure the following line is uncommented in your `httpd.conf` file:

LoadModule cgi_module modules/mod_cgi.so


3. Make sure the CGI scripts are enabled by adding the following lines to the Apache configuration file (`httpd.conf`):

```apache
<Directory "C:/xampp/cgi-bin">
    AllowOverride None
    Options +ExecCGI
    AddHandler cgi-script .cgi .pl .exe
    Require all granted
</Directory>
Step 2: Compile the C++ Program
Navigate to the src folder.

Compile the C++ code using g++ or another C++ compiler:


g++ crud.cpp -o crud.cgi
Move the compiled crud.cgi file to the cgi-bin directory of your web server:


mv crud.cgi /path/to/your/cgi-bin
For XAMPP, it's typically located at C:/xampp/cgi-bin.

Step 3: Place the HTML Files
Move the index.html file into your server's web directory (e.g., htdocs for XAMPP):


mv index.html /path/to/your/web/directory
For XAMPP, it's typically located at C:/xampp/htdocs.

Step 4: Run the Web Application
Start your XAMPP or web server.

Open your browser and go to:


http://localhost/index.html
Use the interface to add, update, or delete records. The data will be stored in the records.txt file.

Usage
Add a Record
Fill in the name, address, and phone number fields and submit the form to add a record.
Update a Record
Enter the name of the record you want to update, along with the new address and phone number.
Delete a Record
Enter the name of the record you want to delete and submit the form to remove it from the list.
License
This project is licensed under the MIT License. You are free to use, modify, and distribute this software under the terms of the MIT License.

Contributing
If you'd like to contribute to this project, feel free to fork the repository and submit a pull request. Any feedback or improvements are welcome!