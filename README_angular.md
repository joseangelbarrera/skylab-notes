# angular-demo-app
angular-demo-app


##ngController
- directive in module ng
The ngController directive attaches a controller class to the view. This is a key aspect of how angular supports the principles behind the Model-View-Controller design pattern.

MVC components in angular:

Model — Models are the properties of a scope; scopes are attached to the DOM where scope properties are accessed through bindings.
View — The template (HTML with data bindings) that is rendered into the View.
Controller — The ngController directive specifies a Controller class; the class contains business logic behind the application to decorate the scope with functions and values
Note that you can also attach controllers to the DOM by declaring it in a route definition via the $route service. A common mistake is to declare the controller again using ng-controller in the template itself. This will cause the controller to be attached and executed twice.