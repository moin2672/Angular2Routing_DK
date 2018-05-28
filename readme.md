# L1.3 Summary
# CHECKLIST: SETTING UP
# Define the base path
<base href="/">

# Import RouterModule
* Use RouterModule.forRoot() for app routes (one time only)
* Use RouterModule.forChild() for features

# CHECKLIST: CONFIGURING ROUTES

# path: Url segment(s) for the route
* No leading slash
* ''for default route; '**' for wildcard route 
* casing matters

# component
* Not string name; not enclosed in quotes
* component must be imported

# order matters

# ACTIVATING A ROUTE

# Add the RouterLink directive as an attribute
* Clickable element
* Enclose in square brackets

# Bind to a link parameters array
* First element is the route Url segment

# L1.0 npm install

## Description

These are the starter files for the Angular Routing course on Pluralsight 

## Installation

1) Open a command prompt in the project's root directory (APM)

2) Type: `npm install`
    This installs the dependencies as defined in the package.json file.
    
3) Type: `npm start`
    This launches the TypeScript compiler (tsc) to compile the application and wait for changes. 
    It also starts the lite-server and launches the browser to run the application.
