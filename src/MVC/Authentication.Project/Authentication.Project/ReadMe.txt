1-	dotnet ef migrations add InitialCreate --project Authentication.Project

2-	dotnet ef database update --project Authentication.Project

--------- E-mail confirm -----------
	Obs:https://sendgrid.com/
1-	dotnet user-secrets set SendGridUser RickAndMSFT
2-	dotnet user-secrets set SendGridKey <key>