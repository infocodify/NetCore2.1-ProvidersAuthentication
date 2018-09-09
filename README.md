# NetCore2.1-ProvidersAuthentication

# Microsoft, Google, and external provider authentication in ASP.NET Core

##  1. Microsoft Account external login setup with ASP.NET Core

a.  Create asp.Net Core Web Application \
b.  Add the following code to the Startup.cs file:
```csharp
  services.AddAuthentication().AddMicrosoftAccount(microsoftOptions =>
            {
                microsoftOptions.ClientId = Configuration["Authentication:Microsoft:ApplicationId"];
                microsoftOptions.ClientSecret = Configuration["Authentication:Microsoft:Password"];
            }
```
c. Create the app in Microsoft Developer Portal \
d. Navigate to https://apps.dev.microsoft.com and create or sign into a Microsoft account \
e. Right click on the project, Manage User Secrets and save the Client Id and Password in the secret.json file (so out of your source control)
```json
{
  "Authentication:Microsoft:ApplicationId": "Microsoft App Id Here",
  "Authentication:Microsoft:Password": "App Password Here",
}
```
f. Rename About to Tutorials page (in controller, _layout, and View) and add Authorize to the Controller to access the page view only after login successfully
```csharp
        [Authorize]
        public IActionResult Tutorials()
        {
            ViewData["Message"] = "Your application description page.";

            return View();
        }
```       
##  2. Follow the steps on Microsoft Docs to setup Google external login \
Link: https://docs.microsoft.com/en-us/aspnet/core/security/authentication/social/google-logins?view=aspnetcore-2.1&tabs=aspnetcore2x

