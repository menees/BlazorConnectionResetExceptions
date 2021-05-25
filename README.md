# BlazorConnectionResetExceptions

This repo is for [ASP.NET Core Issue #30127](https://github.com/dotnet/aspnetcore/issues/30127).

It's a minimal repro for producing hundreds of Microsoft.AspNetCore.Connections.ConnectionResetException
and System.Net.Sockets.SocketException messages in the VS 2019 debugger Output window when debugging a Blazor WebAssembly .NET 5
application that connects to an ASP.NET Core server running in Kestrel.

Build and debug the application, go to its "Fetch data" screen, and click its button twice. Each click loads
some data from the server and then uses [NavigationManager.NavigateTo](https://docs.microsoft.com/en-us/dotnet/api/microsoft.aspnetcore.components.navigationmanager.navigateto?view=aspnetcore-5.0)
to reload the page with the forceLoad parameter set to true.