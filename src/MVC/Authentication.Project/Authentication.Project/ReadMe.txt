1-	dotnet ef migrations add InitialCreate --project Authentication.Project

2-	dotnet ef database update --project Authentication.Project

--------- E-mail confirm -----------
	Obs:https://sendgrid.com/
1-	dotnet user-secrets set SendGridUser NoReply
2-	dotnet user-secrets set SendGridKey <key>
3-	Scaffold Account/RegisterConfirmation
	DisplayConfirmAccountLink = false;

----------- Facebook Authentication ------------
1-	Install-Package Microsoft.AspNetCore.Authentication.Facebook -Version 3.1.7
2-	dotnet user-secrets set "Authentication__Facebook__AppId" "<app-id>"
3-	dotnet user-secrets set "Authentication__Facebook__AppSecret" "<app-secret>"

-------------- Google Authentication -----------------
1-	Install-Package Microsoft.AspNetCore.Authentication.Google -Version 3.1.7
2-	dotnet user-secrets set "Authentication:Google:ClientId" "<client-id>"
3-	dotnet user-secrets set "Authentication:Google:ClientSecret" "<client-secret>"
