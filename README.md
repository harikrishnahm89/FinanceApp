# 💰 FinanceApp

A simple **Expense Tracking Web Application** built using **ASP.NET MVC 5**, **Entity Framework 6**, and **SQL Server**.  
It helps users record their daily expenses, categorize them, and visualize spending using interactive **Chart.js** charts.

---

## 🚀 Features

- 🧾 Add, view, and manage expenses  
- 🗂️ Categorize expenses (e.g., Rent, Food, Utilities, Entertainment)  
- 📊 Visualize total spending per category with **Chart.js pie charts**  
- 💾 Data persistence using **Entity Framework (Code-First)**  
- 🌐 Clean and responsive **Bootstrap UI**  
- ⚙️ Built following MVC architecture and best practices  

---

## 🖥️ Tech Stack

| Layer | Technology |
|-------|-------------|
| **Frontend** | HTML5, CSS3, Bootstrap, JavaScript, Chart.js |
| **Backend** | ASP.NET MVC 5, C# |
| **Database** | SQL Server 2019, Entity Framework 6 |
| **IDE** | Visual Studio 2022 |
| **Version Control** | Git & GitHub |

---

## 🏗️ Project Architecture

FinanceApp/
│
├── Controllers/
│ ├── HomeController.cs
│ ├── ExpensesController.cs
│
├── Models/
│ ├── Expense.cs
│ └── ErrorViewModel.cs
│
├── Data/
│ ├── FinanceAppContext.cs
│ ├── Service/
│ ├── IExpensesService.cs
│ └── ExpensesService.cs
│
├── Views/
│ ├── Expenses/
│ │ ├── Index.cshtml
│ │ ├── Create.cshtml
│ └── Shared/
│ ├── _Layout.cshtml
│
└── wwwroot/
├── css/
├── js/
├── lib/


---

## 📊 Chart.js Integration

The app uses `Chart.js` to visualize expenses by category:

```js
fetch('/Expenses/GetChart')
  .then(response => response.json())
  .then(data => {
    new Chart(document.getElementById('myChart'), {
      type: 'pie',
      data: {
        labels: data.map(d => d.category),
        datasets: [{
          data: data.map(d => d.total)
        }]
      }
    });
  });


