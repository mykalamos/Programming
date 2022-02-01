# Model View Controller
https://docs.microsoft.com/en-us/aspnet/core/mvc/overview?WT.mc_id=dotnet-35129-website&view=aspnetcore-6.0

- Separation of concerns
- User requests ➡️ Controller (c)
- (C) + Model (M) to
  - Perform user actions
  - Retrieve results of queries
- (C) chooses the View (V) to display to the user
  - Provides (V) with any Model data it requires

- (C) ➡️ (V) ➡️ (M)

- Delineation of responsibilites. Enables scaling due to ease of
  1. code
  2. debug
  3. test
