
# Spring Boot Project with H2 Database and Apache POI

This is a **Java Spring Boot** project that uses an **H2 Database** in-memory to store data imported from an Excel spreadsheet. The project also uses **Apache POI** to process the spreadsheet and populate the database. Additionally, there is a feature to generate and download a report with the users' data.

## Features
- **In-Memory Database (H2)**: Stores data extracted from the Excel spreadsheet.
- **Data Import**: Populates the database with data from an Excel spreadsheet using Insomnia.
- **Excel Report**: Generates a report with users' data, available for download.

## How to Set Up

### 1. Run the Application
Clone this repository and run the Spring Boot application:

```bash
mvn spring-boot:run
```

The application will start at: `http://localhost:8080`

### 2. Import Data from Excel via Insomnia

You can import the data from the Excel file using **Insomnia**.

To make it even easier, the Insomnia request configuration file (Insomnia_2024-11-15.json) has been included. 
You only need to import this file into Insomnia, and it will automatically set up the necessary request.

The Excel file should have the following structure:

| Nome           | Idade | Data Nascimento | Saldo   |
|-------------|-------|-----------------|---------|
| João Silva  | 30    | 01/01/1996      | 1000.50 |
| Maria Souza | 25    | 03/03/2000      | 1500.75 |


After importing the Insomnia_2024-11-15.json file, create a POST request in Insomnia to upload the Excel file:

- **Method**: POST
- **URL**: `http://localhost:8080/api/users/`
- **Body**: Form-data with the key `file` and the attached Excel file.

Example Request:
```json
POST http://localhost:8080/api/users/
```

### 3. Generate the Users' Report

After importing the data, you can download the generated report by accessing the following URL:

- **URL to download the report**: [http://localhost:8080/api/users/](http://localhost:8080/api/users/)

This will generate an Excel file named **relatorio_usuarios.xls**, containing all the users' data stored in the database.

## API Endpoints

### 1. Import Data (POST)
- **URL**: `/api/users/`
- **Method**: POST
- **Body**: Form-data with the key `file` and the attached Excel file.

### 2. Generate Users Report (GET)
- **URL**: `/api/users/`
- **Method**: GET
- **Description**: Generates an Excel report with all the users' data.

## Technologies Used

- **Spring Boot** for building the web application.
- **H2 Database** as an in-memory database.
- **Apache POI** for working with Excel files.

## Contributing

If you want to contribute to the project, feel free to fork the repository, create a branch, and submit a pull request with your improvements.

## License

This project is licensed under the [MIT License](LICENSE).
