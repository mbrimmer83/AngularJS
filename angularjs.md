# AngularJS 1

* comparison to jQuery - look at Tic Tac Toe app and look at places where we are updating display of the view.
* MVC
* data binding
* expressions
* directives - AngularJS directives are special HTML attributes that add special behavior to elements
* module
* controller

## ng-app

Tells AngularJS that this DOM element is an AngularJS application and it's behavior will be controlled by AngularJS. The simplest form is

```
<div ng-app>
</div>
```

## Expressions

AngularJS expressions look like this: `{{ name }}`. They have contain
a limited set of JavaScript expression within them, including:

* `1+2`
* `a+b`
* `user.name`
* `items[index]`

Read more about expressions: https://docs.angularjs.org/guide/expression

## ng-model

`ng-model` is applicable only for form input elements, including `input`, `select`, `textarea` or custom form controls. It binds (2-way) the `value` property of the element to a property in the scope. Example

```
<input type="text" ng-model="name">
```

This will bind the input's value to the "name" property within the scope.

## ng-app 2

To link the DOM element to your own AngularJS app written in JavaScript:

```
<div ng-app="my-app">
</div>
```

The above markup initializes the app and initializes it using the corresponding AngularJS app:

```
// whatever you do, don't forget to put an array - can be empty - in as the
// second argument
var app = angular.module('my-app', []);
```

See angular-examples/3.html

## ng-controller

Creating a custom AngularJS module doesn't do anything by itself. To make it do something interesting, you have to create a controller. The controller customarily takes in a $scope argument, to which you can attach properties which will be accessibly within the template.

```
var app = angular.module('my-app', []);
app.controller('MainController', function($scope) {
  $scope.name = 'Camila';
});
```

Then you need to link the controller to the DOM element:

```
<div ng-app="my-app" ng-controller="MainController">
  {{ name }}
</div>
```

## `$scope`

The `$scope` parameter of a controller function is the object that connects your JavaScript controller to the HTML template.


# AngularJS Terms

* data binding - automatic binding of JavaScript values directly into the view - or the DOM
* view - what the user sees of the application, in web applications this is usually the DOM. In AngularJS, this is the template.
* templates - HTML markup with directives and expressions
* directives - AngularJS directives are special HTML attributes that add special behavior to elements
* expressions - expressions substitute into templates values from JavaScript models using property names and other expressions. Ex. `{{ name }}`.
* controller - written in JavaScript, this is usually a big component of AngularJS apps. Controllers determine what happens and how the model objects update when actions are taken by users.
* scope - an object where AngularJS binds properties to. Within a controller, this is usually the `$scope` object.

## Directives

* ng-app - initializes the element as an AngularJS app, optionally tying to an AngularJS module
* ng-init - initializes properties in the scope - usually only used with non-JS AngularJS apps.
* ng-controller - specifies the controller in the module to control this DOM element
* ng-click - the method on the controller to call when element is clicked
* ng-submit - the method on the controller to call when a form is submitted
* ng-show - conditionally show this element depending on the truth value of the expression
* ng-repeat - repeat element based on a array of array-like object
* ng-disabled - conditionally disable this element depending on the truth value of the expression
* ng-model - binds an `<input>`, `<textarea>`, or `<select>` element's value property to a property on the AngularJS scope.
