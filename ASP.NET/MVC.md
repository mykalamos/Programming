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

## Model

- State of the application
- business logic or operations
- persisting the state of the application.
- (V) typically use ViewModel (VM) types designed to contain the data to display on (V)
- (C) creates and populates (VM)s from the (M)

## View

- Presenting content through the user interface.
- Razor view engine to embed .NET code in HTML markup.
- Minimal logic - only for presenting content
- Complex model, consider using a View Component, ViewModel, or view template to simplify the view.

## Controller

- Handle user interaction - intial entry point
- Work with the model
- Select a view to render

## Routing
- URL mapping
- Route template syntax
  - route value constraints
  - defaults
  - optional values
### Convention-based routing
  - Globally define the URL formats that your application accepts and how each of those formats maps to a specific action method on a given controller.
  - Incoming request ➡️ routing engine ➡️ defined URL formats ➡️ controller's action method
### Attribute routing
- Decorating controllers and actions with attributes that define your application's routes

## Model binding
- Converts client request data the controller can handle
  - form values
  - route data
  - query string parameters,
  - HTTP headers
 - Data as parameters to its action methods

## Model Validation
- Validation by decorating model object with data annotation validation attributes.
- Attributes checked on
  - Client side
  - Server side
 ... before the controller action is called.
