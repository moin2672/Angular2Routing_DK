# L2.2 Summary

# Routing to Features Checklist: 

##Configuration

* Import RouterModule
Be sure to use RouterModule.forChild()

* Configure the routes

## Naming Routes

* Use a common root path name for related feature routes

- product
- products/:id
- products/:id/edit

## Activate with code
* Import the Router
* Add a dependency on the Router service
- As a constructor parameter
* Use the Router service navigate method
* Pass in a link parameters array
- First element is the rool Url segment
- All other elements are route parameters or additional Url segments

## Routing Modules
* Seperate out routes to their own routing module
* Keep route path order in mind

# L2.1 Routing user login
Activating a Route with code
// standard syntax
this.route.navigate(['/welcome']);    
// short-cut syntax
this.route.navigate('/welcome');
// complex url syntax   
this.route.navigateByUrl('/welcome'); 

// current route
http://localhost:3000/products(popup:messages)
// navigate()
http://localhost:3000/welcome(popup:messages)
// navigateByUrl
http://localhost:3000/welcome

* Hint:
Router.forChild() access before the Router.forRoot()

# L2.0
 RouterModule.forChild([
      {path: 'products', component: ProductListComponent}
    ])

* Routing for child

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
