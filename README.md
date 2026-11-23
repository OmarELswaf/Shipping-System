# Shipping Management System

ASP.NET Core MVC training project for managing shipments, users and shipping settings. It uses Entity Framework Core with SQL Server and ASP.NET Core Identity.

## What is in the source

- MVC controllers, views and repository classes for orders, employees, traders and representatives
- Branch, city, governorate, village and weight-based shipping settings
- Identity sign-in and claim-based permission policies
- EF Core migrations and a SignalR notification hub

This describes the code in the repository, not an independently verified production deployment. Personal contribution and team attribution still need confirmation.

## Stack

.NET 8, ASP.NET Core MVC, EF Core 8, SQL Server, ASP.NET Core Identity, Bootstrap, SignalR, MailKit.

## Local setup outline

A .NET 8 SDK and an accessible SQL Server instance are required. The steps below follow the project configuration but have not been executed as part of the 23 November 2026 review.

```bash
git clone https://github.com/OmarELswaf/Shipping-System.git
cd Shipping-System
dotnet restore "Shipping System.sln"
```

Configure `ConnectionStrings:DefaultConnection` locally, using an environment variable or .NET user secrets. Do not commit a database password. The application reads this connection-string key in `Program.cs`.

Use EF Core tooling compatible with the project's EF Core 8 dependencies to apply migrations to a dedicated development database. Then start the MVC project:

```bash
dotnet ef database update --project "Shipping System/Shipping System.csproj"
dotnet run --project "Shipping System/Shipping System.csproj"
```

Open the local URL printed by .NET. The default route opens `Account/Login`.

## Verification and known gaps

- No hosted demo is linked here.
- Build, migrations, sign-in and shipment workflows were not run in this review.
- A documented first-admin/test-account bootstrap is still needed. Do not assume a fresh database includes a usable account.
- Password-reset email requires local mail configuration; do not use real recipients in a demo.
- The current password rules allow a four-character password. Review authentication and authorization before any real deployment.
- Generated Visual Studio/build files are tracked in the repository and should be removed from version control in a separate reviewed cleanup.

## Showcase evidence to add

After a successful local run, capture the shipment list, shipment details and a permissions workflow using fictional data. Include the exact build/run steps and clearly credit individual contributions before presenting this as a finished case study.
