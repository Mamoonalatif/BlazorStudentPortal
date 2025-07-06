# 🎓 Blazor Student Portal

A modern, interactive web application built with **Blazor Server** for managing student records with full CRUD (Create, Read, Update, Delete) operations and SQL Server database integration.

![.NET](https://img.shields.io/badge/.NET-8.0-blue)
![Blazor](https://img.shields.io/badge/Blazor-Server-purple)
![SQL Server](https://img.shields.io/badge/SQL%20Server-Database-red)
![License](https://img.shields.io/badge/License-MIT-green)

## 🚀 Features

### ✨ Core Functionality
- **📝 Student Registration**: Add new students with comprehensive form validation
- **📋 Student List Management**: View all registered students in a responsive data table
- **✏️ Student Profile Editing**: Update existing student information seamlessly
- **🗑️ Student Record Deletion**: Remove student records with one-click deletion
- **🔍 Real-time Data Loading**: Dynamic content loading with loading states

### 🎨 User Interface
- **🌟 Modern Animated UI**: Glowing text effects and animated buttons
- **📱 Responsive Design**: Mobile-friendly layout with Bootstrap integration
- **🖼️ Visual Elements**: Student profile images and background graphics
- **🎯 Interactive Forms**: Real-time form handling with EditForm validation
- **⚡ Server-side Rendering**: Fast, interactive server-side components

### 🔧 Technical Features
- **🗄️ SQL Server Integration**: Direct database connectivity using Microsoft.Data.SqlClient
- **🔄 Asynchronous Operations**: Full async/await pattern implementation
- **🛡️ Type Safety**: Strongly-typed models and services
- **📊 Data Access Layer**: Dedicated service layer for database operations
- **⚙️ Configuration Management**: Environment-based connection string management

## 🏗️ Architecture

### 📁 Project Structure
```
📦 BlazorStudentPortal
├── 📂 Components/
│   ├── 📂 Layout/
│   │   ├── 🎨 MainLayout.razor       # Main application layout
│   │   ├── 🎨 MainLayout.razor.css   # Layout styling
│   │   ├── 🧭 NavMenu.razor          # Navigation component
│   │   └── 🎨 NavMenu.razor.css      # Navigation styling
│   ├── 📂 Pages/
│   │   ├── 🏠 StudentsCRUD.razor     # Main CRUD operations page
│   │   └── ❌ Error.razor           # Error handling page
│   ├── 🚀 App.razor                 # Root application component
│   ├── 🛣️ Routes.razor              # Routing configuration
│   └── 📥 _Imports.razor            # Global imports
├── 📂 Data/
│   ├── 👤 Student.cs               # Student data model
│   └── 🔧 StudentService.cs        # Database service layer
├── 📂 wwwroot/
│   ├── 🎨 app.css                  # Global application styles
│   ├── 🖼️ favicon.png              # Application icon
│   ├── 📂 bootstrap/               # Bootstrap CSS framework
│   └── 📂 images/                  # Student images and assets
├── ⚙️ Program.cs                   # Application entry point
├── 🔧 Database.csproj              # Project configuration
└── 📋 appsettings.json             # Application configuration
```

### 🏛️ Architecture Patterns
- **🔧 Service Layer Pattern**: Separation of concerns with dedicated StudentService
- **📋 Repository Pattern**: Centralized data access through service methods
- **🎯 Component-Based Architecture**: Modular Blazor components
- **🔄 Dependency Injection**: Built-in DI for service registration

## 💾 Database Schema

### 👤 Student Table
```sql
CREATE TABLE Students (
    Id INT PRIMARY KEY IDENTITY(1,1),
    Name NVARCHAR(100) NOT NULL,
    Age INT NOT NULL,
    Email NVARCHAR(255) NOT NULL
);
```

### 🔍 Database Operations
- **GET** `/Students` - Retrieve all students
- **GET** `/Students/{id}` - Get student by ID
- **POST** `/Students` - Create new student
- **PUT** `/Students/{id}` - Update existing student
- **DELETE** `/Students/{id}` - Delete student record

## 🛠️ Technology Stack

### 🖥️ Backend Technologies
- **⚡ .NET 8.0** - Latest .NET framework
- **🌐 Blazor Server** - Server-side rendering with real-time updates
- **🗄️ Microsoft.Data.SqlClient 6.0.2** - SQL Server connectivity
- **🔧 ASP.NET Core** - Web application framework

### 🎨 Frontend Technologies
- **🎯 Razor Components** - Component-based UI development
- **📱 Bootstrap** - Responsive CSS framework
- **🎨 Custom CSS** - Animated and glowing UI effects
- **🖼️ Static Assets** - Images and styling resources

### 🗄️ Database
- **🏢 SQL Server Express** - Local database instance
- **🔗 Entity Framework** - Database connectivity layer
- **🔄 Async Data Access** - Non-blocking database operations

## ⚙️ Installation & Setup

### 📋 Prerequisites
- **💻 .NET 8.0 SDK** or later
- **🗄️ SQL Server Express** or SQL Server
- **🔧 Visual Studio 2022** or Visual Studio Code
- **📦 NuGet Package Manager**

### 🚀 Getting Started

1. **📥 Clone the repository**
   ```bash
   git clone https://github.com/Mamoonalatif/BlazorStudentPortal.git
   cd BlazorStudentPortal
   ```

2. **🗄️ Setup Database**
   - Create a new database named `StudentDB` in SQL Server
   - Execute the following SQL script:
   ```sql
   CREATE DATABASE StudentDB;
   USE StudentDB;
   
   CREATE TABLE Students (
       Id INT PRIMARY KEY IDENTITY(1,1),
       Name NVARCHAR(100) NOT NULL,
       Age INT NOT NULL,
       Email NVARCHAR(255) NOT NULL
   );
   ```

3. **⚙️ Configure Connection String**
   - Update `appsettings.json` with your SQL Server connection:
   ```json
   {
     "ConnectionStrings": {
       "DefaultConnection": "Server=YOUR_SERVER;Database=StudentDB;Trusted_Connection=True;Encrypt=False;"
     }
   }
   ```

4. **📦 Restore Dependencies**
   ```bash
   dotnet restore
   ```

5. **🚀 Run the Application**
   ```bash
   dotnet run
   ```

6. **🌐 Access the Application**
   - Open your browser and navigate to `https://localhost:5001` or `http://localhost:5000`

## 💡 Usage Guide

### ➕ Adding a New Student
1. Navigate to the home page
2. Fill in the student registration form:
   - **👤 Name**: Student's full name
   - **🎂 Age**: Student's age (numeric)
   - **📧 Email**: Student's email address
3. Click the **💾 Save** button
4. The new student will appear in the students table

### ✏️ Editing a Student
1. Locate the student in the table
2. Click the **✏️ Edit** button for that student
3. The form will populate with existing data
4. Modify the desired fields
5. Click **💾 Save** to update the record

### 🗑️ Deleting a Student
1. Find the student record in the table
2. Click the **🗑️ Delete** button
3. The student will be immediately removed from the database

### 📋 Viewing All Students
- All registered students are displayed in the responsive data table
- The table shows: **ID**, **Name**, **Age**, **Email**, and **Actions**
- Data is loaded asynchronously with loading indicators

## 🎨 UI Features

### ✨ Visual Effects
- **🌟 Glowing Text**: Animated title with CSS glow effects
- **🎯 Animated Buttons**: Hover effects and transitions
- **🖼️ Student Images**: Profile pictures and background graphics
- **📱 Responsive Layout**: Mobile-first design approach

### 🎨 Styling Components
- **Custom CSS animations** for enhanced user experience
- **Bootstrap integration** for responsive grid system
- **Professional color scheme** with modern aesthetics
- **Interactive form elements** with visual feedback

## 🔧 Configuration

### 📋 Application Settings
```json
{
  "Logging": {
    "LogLevel": {
      "Default": "Information",
      "Microsoft.AspNetCore": "Warning"
    }
  },
  "AllowedHosts": "*",
  "ConnectionStrings": {
    "DefaultConnection": "Server=MAMOONA\\SQLEXPRESS;Database=StudentDB;Trusted_Connection=True;Encrypt=False;"
  }
}
```

### 🔧 Service Registration
```csharp
builder.Services.AddRazorComponents()
    .AddInteractiveServerComponents();
builder.Services.AddScoped<StudentService>();
```

## 🤝 Contributing

1. **🍴 Fork** the repository
2. **🌿 Create** a feature branch (`git checkout -b feature/AmazingFeature`)
3. **💾 Commit** your changes (`git commit -m 'Add some AmazingFeature'`)
4. **📤 Push** to the branch (`git push origin feature/AmazingFeature`)
5. **🔄 Open** a Pull Request

## 📄 License

This project is licensed under the **MIT License** - see the [LICENSE](LICENSE) file for details.

## 👨‍💻 Author

**Mamoona Latif**
- 🐙 GitHub: [@Mamoonalatif](https://github.com/Mamoonalatif)
- 📧 Email: [Your Email]
- 💼 LinkedIn: [Your LinkedIn Profile]

## 🙏 Acknowledgments

- **Microsoft** for the amazing Blazor framework
- **Bootstrap** team for the responsive CSS framework
- **SQL Server** team for the robust database engine
- **Open Source Community** for continuous inspiration

---

⭐ **Star this repository** if you found it helpful!

🐛 **Found a bug?** Please open an issue!

💡 **Have a suggestion?** We'd love to hear from you!
