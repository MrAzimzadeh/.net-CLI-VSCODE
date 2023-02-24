Asp.NET AREA

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
  
