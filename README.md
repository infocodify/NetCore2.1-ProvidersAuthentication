# NetCore2.1-ProvidersAuthentication
Microsoft, Google, and external provider authentication in ASP.NET Core

#1. Microsoft Account external login setup with ASP.NET Core

a.  Create asp.Net Core Web Application \n
b.  Add the following code to the Startup.cs file:
```csharp
  services.AddAuthentication().AddMicrosoftAccount(microsoftOptions =>
            {
                microsoftOptions.ClientId = Configuration["Authentication:Microsoft:ApplicationId"];
                microsoftOptions.ClientSecret = Configuration["Authentication:Microsoft:Password"];
            }
```                
