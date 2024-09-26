
#### What is .NET Framework?
- It's a software development platform by Microsoft that's used to build applications on multiple operating systems such as Windows, MacOS, Linux, etc. 

#### What is CLR? 
- CLR (Common Language Runtime), manages the execution of .NET applications. 
- Manages memory management, exception handling, security management. 

#### What is CTS and CLS?
- The **Common Type System (CTS)** and **Common Language Specification (CLS)** ensure that code written in different languages can work together within the .NET framework. 

#### What is the ASP.NET MVC Pattern?
- It is an architecture that separates an application into three components: the model, the view, and the controller. 

MVC stands for Model-View-Controller

Data ~ Model
User-Interface ~ View
Application Logic ~ Controller

#### **Model:**
- Represents the core logic and data of an application. It's responsible for retrieving and managing data from databases, APIs, and business logic. 
- The model doesn't know about the view or controller as it only focuses on data and logic. 

Functions: 
- Manages data, both reading and writing to a database
- Implements business logic 
- Notifies the **View** when data changes so the UI can be updated
#### **View:**
- Responsible for displaying the data and the UI. It renders the UI data from the Model and defines that the user will see. 

Functions: 
- Displays data and provides a UI
- Represents the layer in JavaScript, HTML, CSS
- Retrives data from the Model to show the user
- Includes dynamic content such as forms or surveys that can be used to interact with the user

#### **Controller:**
- It is a link between the Model and View. It handles user input (e.g., form submissions, clicks, surveys, etc.), processes it, updates the Model as it sees fit and returns a View to the user. 

Functions: 
- Retrieves and processes user input from the View
- Interacts with the Model to retrieve or update data
- Decides which View should be rendered based on the user’s actions.
- Contains the application flow and orchestrates what happens next in the application
### General Concepts within .Net

##### What are Razor Pages used for?
- Razor pages are used on individual pages that combine UI and logic
- Each Razor page is self-contained, with its own HTML and C# code for handling UI
- Ideal for static content pages and building web UIs and APIs
###### Structure of a Razor Page

A Razor Page consists of two files:
- **Page.cshtml**: The view part, which contains HTML and Razor syntax.
- **Page.cshtml.cs**: The code-behind file, which contains the C# logic for that page

CRUD:
- Create
- Read
- Update
- Delete


