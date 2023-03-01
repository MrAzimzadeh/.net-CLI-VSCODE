# Create Mvc(Area & SqlLite)
```bash
 dotnet new mvc --auth Individual
```
# Asp.Net Identity <br/>
## Only written name
```bash
dotnet aspnet-codegenerator identity -dc WebApp.Data.AppDbContext  --files "Accoun
t.Register;Account.Login;Account.Logout" // 
```
## All
```bash 
dotnet aspnet-codegenerator identity -dc WebApp.Data.AppDbContext  // all
```

## Error : The below files exist. Use '--force' to overwrite: Areas/Identity/Pages/Account/Login.cshtml
```bash 

dotnet aspnet-codegenerator identity -dc WebApp.Data.AppDbContext  --force
```

# Asp.NET AREA
```bash 
dotnet tool install -g dotnet-aspnet-codegenerator
dotnet add package Microsoft.VisualStudio.Web.CodeGeneration.Design 

dotnet-aspnet-codegenerator area Admin
```

Area Program.cs

```c#


app.UseEndpoints(endpoints =>
    {
    endpoints.MapControllerRoute(
      name: "areas",
      pattern: "{area:exists}/{controller=Home}/{action=Index}/{id?}"
    );
});
```

Data(DbContext)

```c#
public AppDbContext(DbContextOptions<AppDbContext> options) :base(options) { }
```
Data json 
```Json
  "ConnectionStrings": {
    "DefaultConnection": "Server=;Database=;Trusted_Connection=true;TrustServerCertificate=True;"
  },
```
Sql server ConnectionStrings
```c#
builder.Services.AddDbContext<AppDbContext>(x => x.UseSqlServer(builder.Configuration.GetConnectionString("DefaultConnection")));

```
  
