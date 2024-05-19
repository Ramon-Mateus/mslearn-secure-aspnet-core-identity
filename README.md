# Welcome!

This is the starter project for [Secure a .NET web app with the ASP.NET Core Identity framework](https://docs.microsoft.com/learn/modules/secure-aspnet-core-identity/). A completed version of the project is located on the `solution` branch.

# Contributing

This project welcomes contributions and suggestions.  Most contributions require you to agree to a
Contributor License Agreement (CLA) declaring that you have the right to, and actually do, grant us
the rights to use your contribution. For details, visit https://cla.opensource.microsoft.com.

When you submit a pull request, a CLA bot will automatically determine whether you need to provide
a CLA and decorate the PR appropriately (e.g., status check, comment). Simply follow the instructions
provided by the bot. You will only need to do this once across all repos using our CLA.

This project has adopted the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/).
For more information see the [Code of Conduct FAQ](https://opensource.microsoft.com/codeofconduct/faq/) or
contact [opencode@microsoft.com](mailto:opencode@microsoft.com) with any additional questions or comments.

# Legal Notices

Microsoft and any contributors grant you a license to the Microsoft documentation and other content
in this repository under the [Creative Commons Attribution 4.0 International Public License](https://creativecommons.org/licenses/by/4.0/legalcode),
see the [LICENSE](LICENSE) file, and grant you a license to any code in the repository under the [MIT License](https://opensource.org/licenses/MIT), see the
[LICENSE-CODE](LICENSE-CODE) file.

Microsoft, Windows, Microsoft Azure and/or other Microsoft products and services referenced in the documentation
may be either trademarks or registered trademarks of Microsoft in the United States and/or other countries.
The licenses for this project do not grant you rights to use any Microsoft names, logos, or trademarks.
Microsoft's general trademark guidelines can be found at http://go.microsoft.com/fwlink/?LinkID=254653.

Privacy information can be found at https://privacy.microsoft.com/en-us/

Microsoft and any contributors reserve all other rights, whether under their respective copyrights, patents,
or trademarks, whether by implication, estoppel or otherwise.

# Comandos utilizados no desenvolvimento

Esses comandos fazem o projeto ter suporte ao Identity e construir uma autenticação de usuário padrão.
```shell
dotnet tool install dotnet-aspnet-codegenerator --version 6.0.2 --global

dotnet add package Microsoft.VisualStudio.Web.CodeGeneration.Design --version 6.0.2
dotnet add package Microsoft.AspNetCore.Identity.EntityFrameworkCore --version 6.0.3
dotnet add package Microsoft.AspNetCore.Identity.UI --version 6.0.3
dotnet add package Microsoft.EntityFrameworkCore.Design --version 6.0.3
dotnet add package Microsoft.EntityFrameworkCore.SqlServer --version 6.0.3

dotnet aspnet-codegenerator identity --useDefaultUI --dbContext RazorPagesPizzaAuth

dotnet build
dotnet tool install dotnet-ef --version 6.0.3 --global
dotnet ef migrations add CreateIdentitySchema
dotnet ef database update
```

Esse comando adiciona ao projeto os arquivos de registro do usuário a serem modificados:
```shell
dotnet aspnet-codegenerator identity --dbContext RazorPagesPizzaAuth --files "Account.Manage.EnableAuthenticator;Account.Manage.Index;Account.Register;Account.ConfirmEmail" --userClass RazorPagesPizzaUser --force
```
