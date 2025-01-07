# How to Run a Clean Architecture Web Project in .NET MVC

## Prerequisites

Ensure you have the following installed:

- [Visual Studio](https://visualstudio.microsoft.com/) (preferably the latest version)
- [.NET SDK](https://dotnet.microsoft.com/download)
- SQL Server or another supported database system
- Git (optional, for cloning the repository)

---

## Step 1: Clone or Download the Project

If the project is hosted on a Git repository, clone it:

```bash
git clone 'https://github.com/ahmadrajpoot062/FYDP-Prototype-and-Implementation'
```

Alternatively, download the project as a ZIP file and extract it to your preferred directory.

---

## Step 2: Open the Solution in Visual Studio

1. Launch Visual Studio.
2. Navigate to **File > Open > Project/Solution**.
3. Open the `.sln` file located in the project root directory.

---

## Step 3: Restore NuGet Packages

Restore all the necessary dependencies:

1. Open the **Tools** menu.
2. Select **NuGet Package Manager > Manage NuGet Packages for Solution**.
3. Click on **Restore** or run the following command in the **Package Manager Console**:

   ```bash
   dotnet restore
   ```

---

## Step 4: Set Up the Database

1. Locate the **appsettings.json** file in the `Web` or `API` project.
2. Update the connection string under `ConnectionStrings` with your database credentials:

   ```json
   "ConnectionStrings": {
       "DefaultConnection": "Server=YOUR_SERVER;Database=YOUR_DATABASE;User Id=YOUR_USERNAME;Password=YOUR_PASSWORD;"
   }
   ```

3. Open the **Package Manager Console** and run the following commands to apply migrations and seed data:

   ```bash
   Update-Database
   ```

   Alternatively, use the .NET CLI:

   ```bash
   dotnet ef database update
   ```

---

## Step 5: Configure Startup Project

1. Right-click on the `Web` or `API` project (depending on the architecture) in the **Solution Explorer**.
2. Select **Set as Startup Project**.

---

## Step 6: Run the Application

1. Press **F5** or click the **Run** button in Visual Studio.
2. The application should build and launch in your default browser.

---

## Step 7: Verify the Application

- Navigate to the appropriate endpoints to verify the application is running as expected.
- Check the logs or console for any errors or warnings.

---

## Troubleshooting

### Common Issues

1. **Missing Dependencies:**
   - Ensure all NuGet packages are restored.

2. **Database Connection Errors:**
   - Double-check your connection string in `appsettings.json`.

3. **Build Errors:**
   - Ensure the .NET SDK version matches the project requirements.

4. **Migration Issues:**
   - Check for pending migrations using:

     ```bash
     dotnet ef migrations list
     ```
---
