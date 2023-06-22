# Property Binding

https://angular.io/guide/property-binding

https://stackblitz.com/~/github.com/luiscoco/AngularTemplate_Sample3-PropertyBinding

In Angular, property binding is a mechanism that allows you to bind the value of a component property to an expression. It enables you to dynamically set or update the value of an HTML element property using a component's property.

Property binding is denoted by square brackets ([]) surrounding the target property within the HTML template. The expression inside the brackets is evaluated, and its value is assigned to the specified property.

Here's a simple example to demonstrate property binding in Angular:

Let's assume we have a component called AppComponent with a property called message. We want to bind this property to the textContent property of a <span> element in our template.
  
```typescript
  // app.component.ts
import { Component } from '@angular/core';

@Component({
  selector: 'app-root',
  template: `
    <span [textContent]="message"></span>
  `,
})
export class AppComponent {
  message = 'Hello, Angular!';
}
```

In this example, we're using property binding to bind the message property of the AppComponent to the textContent property of the span element. The value of message will be displayed within the span element.

When Angular renders the template, it evaluates the expression message and assigns its value ('Hello, Angular!') to the textContent property of the span element.

You can also bind to properties of built-in HTML elements or custom components, as long as they have corresponding properties. 

In these examples, the imageUrl property is bound to the src property of the img element, and the inputValue property is bound to the value property of the input element. Any changes to the component properties will automatically update the corresponding element properties.

Property binding is a powerful feature in Angular that allows you to create dynamic and interactive templates by binding component properties to HTML element properties. Here's an example:

```typescript
import { Component } from '@angular/core';

@Component({
  selector: 'app-root',
  template: `
    <img [src]="imageUrl" alt="Image">
    <input [value]="inputValue" (input)="onInputChange($event.target.value)">
  `,
})
export class AppComponent {
  imageUrl = 'https://example.com/image.jpg';
  inputValue = '';

  onInputChange(value: string) {
    this.inputValue = value;
  }
}
```
 
In this example, we have an AppComponent with two properties: imageUrl and inputValue. The imageUrl property represents the URL of an image, and the inputValue property holds the value of an input field.

The imageUrl property is bound to the src property of the img element using property binding. It sets the initial value of the src property to 'https://example.com/image.jpg'.

The inputValue property is bound to the value property of the input element using property binding. It initially sets the value of the input field to an empty string. Additionally, we have an (input) event binding that triggers the onInputChange() method whenever the user types in the input field. The method receives the new value as an argument and updates the inputValue property accordingly.

With this setup, any changes to the imageUrl or inputValue properties in the component will automatically update the corresponding elements in the template, providing a seamless two-way binding between the component and the template.
 
