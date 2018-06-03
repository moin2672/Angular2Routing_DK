# L4.2 using snapshot 
* unable to route based on id value

# L4.1 route resolver product-details
* Using a route resolver
1. Build and register a route resolver service
2. Add resole to the route configuration
3. Read the data from ActivatedRoute


# L3.5 Summary

* Route Parameters Checklist

# # Required Parameters
* Pass needed data on a route
Ex: Detail component requires an id

* Required Parameters
Configure
---------

{path: 'product/:id', component: ProductDetailComponent}

Populate
--------
<a [routerLink]="['/products', product.id]">..</a>
this.router.navigate(['/products',this.product.id])

Read
----
this.route.snapshot.params['id'];
Or Observable
-------------

# #Optional Parameters

* Pass optional or complex information to a route
Eg:
- Search component passes search criteria to the list component to filter the data

* Optional Parameters
Not Configured
--------------
{path: 'products', component: ProductListComponent}

Populate
--------
<a [routerLink]="['/products',{start: startDate, end: endDate}]">...</a>
this.router.navigate(['/products', {start: startDate, end: endDate}]);

Read
----
this.route.snapshot.params['start'];
Or Observable
-------------

# # Query Parameters
Pass optional or complex information to a route that is optionally retained across routes
Eg: List component passes its current user selections to the Detail component which passes them back

* Query Parameters
Not Configured
--------------
{path: 'products', component: ProductListComponent}

Populate
--------
<a [routerLink]="['/products']"
   [queryParams]="{filterBy: 'x', showImage: true}">...</a>
this.router.navigate(['/products', queryParams:{filterBy: 'x', showImage: true}]);

Read
----
this.route.snapshot.queryParams['filterBy'];
Or Observable
-------------

# L3.4 reading Query Parameters

* use ActivatedRouteservice

1. import ActivatedRoute
2. define in constructor

# L3.3 defining query params
* Defining Query Parameters

In template
<a [routerLink] ="['/products', product.id]"
   [queryParams]="{filterBy: 'er' , showImage: true}">
{{product.productName}}
</a>

In component class
this.router.navigate(['/products'],
{
	queryParams: {filterBy: 'er', showImage: true}
}
);

* Retaining Query Parameters (v4+)

Template
--------
<a [routerLink] ="['/products']"
   queryParamsHandling="preserve">
Back
</a>

Component class
---------------

this.router.navigate(['/products'], {queryParamsHandling: 'preserve'});

# L3.2 routing with params using observable
* Reading Route Parameters

Snaphot

1. To read the parameters only once 
2. simple code
3. Eg:
let id = this.route.snapshot.params['id'];

Observable

1. To watch for parameter changes
2. More complex code
3. Eg:
this.route.params.subscribe(
   params=>{
	  let id = params['id'];
	}
);

* Reading Route Parameters (v4+) --> snapshot

import {ActivatedRoute} from '@angular/router';

...

	constructor (private route: ActivatedRoute) {
		console.log(this.route.snapsot.paramMap.get('id');
	}

* Reading Route Parameters (v4+) --> subscribe

import {ActivatedRoute} from '@angular/router';

...

	constructor(private route: ActivatedRoute){
		this.route.paramMap.subscribe(
			params => {
				console.log(params.get('id'));
			}
		);
	}

# L3.1 routing with params

* populating route parameters

<a [routerLink] = "['/products',product.id]">{{product.productName}}</a>
<a [routerLink] = "['/products',product.id,'edit']">Edit</a>
<a [routerLink] = "['/products',0,'edit']">Add Product</a>

this.router.navigate(['/product',this.product.id]);

* Reading route parameters

use ActivatedRoute service

constructor( private route: ActivatedRoute) {}

let id = this.route.snapshot.params['id'];

observable
----------

this.route.params.subscribe(
params => { let id = params['id'] }
);

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
