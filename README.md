# Weather-api
Prerequisites
Before you begin, ensure you have installed the following

Install the .NET Core SDK 6. Download link can be found here - Choose an operating system of your choice to download SDK.
Install the ASP.NET Core Runtime 6. Download link can be found here - Choose runtime for your OS
Install development tools.
Visual Studio 2022 community edition or Visaul Code is the preferred IDE

Windows: Download Viual Studio 2022 community or Visual Studio Code here
Mac or Linux: Download Visual Studio Code here You can also use rider
The installation guide for Visual Studio can be followed here
The setting up of Visual Studio Code can be followed here
Setup project
Clone the repository git clone https://github.com/TomisinFagbola/weather-api

Create appsettings.Development.json and add the following

{
     "ConnectionStrings": {
         "DefaultConnection": "Server=;Database=;UserId=;Password=;MultipleActiveResultSets=true" ## For Postgres Database
         "DefaultConnection1": "Server=;Database=;Trusted_Connection=True; ## For Sql Servver Connection
     },
    
     "SENDGRID_KEY": "", ##  A Sengrid Key needed for the emails
     "SENDER_EMAIL": "" ## An email from which the emails would be sent needed
}
cd API

Run dotnet restore to install package dependencies

Run dotnet build to build the application

Database Migration
Entity Framework Core tools
dotnet ef must be installed as a global or local tool. Install dotnet ef as a global tool with the following command: dotnet tool install --global dotnet-ef
In the terminal change directory into the API project directory
Apply the migration to the database to create the schema. dotnet ef database update
Visit this link here for more information on using ef core tool

Running the application locally on your machine
Make sure all the above instructions are done completely before running the application

If you are using Visual Studio

Right click on the API project and select Set as Startup Project
Then press the F5 to run the application or click on the IIS Express run button on the standard toolbar to run the application
If you are using Visual Studio Code

In your terminal, change directory into src/API directory where the solution file is located and then run the following: dotnet restore dotnet run
The above commands will restore missing application packages, build and then run the application
Either ways will make the project web APIs accessible on Swagger through this http://localhost:7009/swagger/index.html

Migrations
cd src/API
dotnet ef migrations add [NextMigrationName]
dotnet ef migrations script [LastMigrationName] --idempotent
LastMigrationName = Initial
