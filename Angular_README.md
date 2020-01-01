Versions of Angular: 1,2,3,4,5,6,7,8

FrontEnd development framework developed by google, MVVM(mode view view-modal).
Angular is for SPA applications(Page loading is not required)
Based on Javascript, Typescript(Superset of TypeScript)
IVY Engine- Next generaration compilation and rendering pipeline, which reduces the bundle size.faster in slower networks.
Differential loading - It is a process by which the browser chooses between modern (es2015) or legacy javascript(es5).

Setup: Node 10.9.0 > 
npm install -g @angular/cli -> which installs angular cli
Angular CLI to create projects, generate application and library code, and perform a variety of ongoing development 
tasks such as testing, bundling, and deployment.
ng new my-app
cd my-app
ng serve --open

Structure of Angular:
index.html 
 <app-root></app-root> // selector mentioned in *.component.ts
 
main.ts
import { enableProdMode } from '@angular/core';
import { platformBrowserDynamic } from '@angular/platform-browser-dynamic'; // non-relative path
import { AppModule } from './app/app.module'; // relative path
import { environment } from './environments/environment';

if (environment.production) {
  enableProdMode();
}
platformBrowserDynamic().bootstrapModule(AppModule)
  .catch(err => console.error(err));
ngSwitch:
  <div class="terminal" [ngSwitch]="selection.value">
      <pre *ngSwitchDefault>ng generate component xyz</pre>
      <pre *ngSwitchCase="'material'">ng add @angular/material</pre>
      <pre *ngSwitchCase="'dependency'">ng add _____</pre>
      <pre *ngSwitchCase="'test'">ng test</pre>
      <pre *ngSwitchCase="'build'">ng build --prod</pre>
  </div>
  
  
  .circle-link {
    height: 40px;
    width: 40px;
    border-radius: 40px;
    margin: 8px;
    background-color: white;
    border: 1px solid #eeeeee;
    display: flex;
    justify-content: center;
    align-items: center;
    cursor: pointer;
    box-shadow: 0 1px 3px rgba(0, 0, 0, 0.12), 0 1px 2px rgba(0, 0, 0, 0.24);
    transition: 1s ease-out;
  }

  .circle-link:hover {
    transform: translateY(-0.25rem);
    box-shadow: 0px 3px 15px rgba(0, 0, 0, 0.2);
  }

app.component.ts:
import { Component } from '@angular/core';

@Component({
  selector: 'app-root',
  templateUrl: './app.component.html',
  styleUrls: ['./app.component.css']
})
export class AppComponent {
  name = 'Sathish';
}

app.module.ts:
import { BrowserModule } from '@angular/platform-browser';
import { NgModule } from '@angular/core';
import { FormsModule } from '@angular/forms';
import { AppComponent } from './app.component';

@NgModule({
  declarations: [
    AppComponent
  ],
  imports: [
    BrowserModule,
    FormsModule
  ],
  providers: [],
  bootstrap: [AppComponent]
})
export class AppModule { }

app.component.html:
<label for="fName">First Name: </label>
<input type="text" name="fName" [(ngModel)]="name"/>
<p>{{ name }}</p>

Integrating with bootstrap:
 npm i --save bootstrap
Copy relative path of node_modules/bootstrap/dist/css/bootstrap.css and paste it in angular.json as below:
            "styles": [
              "src/styles.css",
              "node_modules/bootstrap/dist/css/bootstrap.css"
            ],


Creating a component:
ng generate component SubServer

DataBidning: Communication between component and template
Two types of dataminding.
1, String interpolation
2, ngmodel

[] -> property binding
() -> event binding
[()] -> Two waybinding

Diectives:
ng generate directive "directive name"
Components
Structual -> ngIf, ngFor
Attribute -> ngStyle
ngIf example:

Component.ts:
```
  flag = true;
  toggleFlag() {
    this.flag = !this.flag;
    return this.flag;
  }
```
component.html:
```<p *ngIf="flag; else elseblock">Flag is true</p>
<ng-template #elseblock>
    <p>Flag is false</p>
</ng-template>
```
ngStyle:
component.ts
  ```getColor() {
    if(this.flag) {
      return "green";
    } else{
      return "red";
    }
  }
```

component.html
```<h1 [ngStyle]="{color: getColor()}">Below is the example of ngif, which internally serves ngstyle</h1>
<h2 [ngClass]="{white: flag}">This is example of ngclass</h2>
<button (click)="toggleFlag()">Toggle Flag</button> 
```
ngFor:
component.html:
```
<h3>Example of ngFor</h3>
<input type="text" placeholder="name" [(ngModel)]="currentName"/>
<button (click)="addStudent()">Add Student</button>
<li *ngFor="let name of studentsList"> {{name}} </li> 
```
Auto Coding plugi: "emmet" available for vscode

SubComponent:
ng g c shopping-list/shopping-edit skipTests true

Custom Directive:
GraphQL
Dec 26, 2019by Sai gowtham
Creating custom directives in angular 8
Home » angular » Creating custom directives in angular 8
Angular
2min read
Creating custom directives in angular 8Creating custom directives in angular 8
In this tutorial, we will learn about how to create a custom directive in angular with the help of examples.

reactgo.com recommended course
Angular 8 - The Complete Guide (2019+ Edition)
What is a Directive?
Directives are custom HTML attributes which tell angular to change the style or behavior of the dom elements.

Creating custom directive
We are creating a custom directive called emoji which helps us to add emojis to our HTML elements.

Now open your terminal and run below command to generate a new directive.

ng generate directive emoji
Now you can see two new files are generated by the angular cli.

angular-directive-file

Open your emoji.directive.ts file and replace with below code.

emoji.directive.ts
import { Directive, ElementRef, OnInit } from '@angular/core';

@Directive({
  selector: '[appEmoji]'
})
export class EmojiDirective implements OnInit {

  constructor(private el: ElementRef) {}

   ngOnInit() {
    this.el.nativeElement.textContent +=️ '✌️';
  }
}GraphQL
Dec 26, 2019by Sai gowtham
Creating custom directives in angular 8
Home » angular » Creating custom directives in angular 8
Angular
2min read
Creating custom directives in angular 8Creating custom directives in angular 8
In this tutorial, we will learn about how to create a custom directive in angular with the help of examples.

reactgo.com recommended course
Angular 8 - The Complete Guide (2019+ Edition)
What is a Directive?
Directives are custom HTML attributes which tell angular to change the style or behavior of the dom elements.

Creating custom directive
We are creating a custom directive called emoji which helps us to add emojis to our HTML elements.

Now open your terminal and run below command to generate a new directive.

ng generate directive emoji
Now you can see two new files are generated by the angular cli.

angular-directive-file

Open your emoji.directive.ts file and replace with below code.

import { Directive, ElementRef, OnInit } from '@angular/core';
```
@Directive({
  selector: '[appEmoji]'
})
export class EmojiDirective implements OnInit {
  constructor(private el: ElementRef) {}
   ngOnInit() {
    this.el.nativeElement.textContent +=️ '✌️';
  }
}
```
in html,:
```
<div style="text-align:center">
  <h1 appEmoji>Welcome to Angular</h1>
</div>
```
Passing values to custom directive using @Input:
```
import { Directive, ElementRef, Input, OnInit } from '@angular/core';
@Directive({
  selector: '[appEmoji]'
})
export class EmojiDirective implements OnInit {
  @Input('appEmoji') emoji: string;
  constructor(private el: ElementRef) { }
  ngOnInit() {
    this.el.nativeElement.textContent += this.emoji;
  }
}
```
in html:
```
<div style="text-align:center">
  <h1 appEmoji="👌">Welcome to Angular</h1>
</div>
```
https://www.positronx.io/creating-custom-directives-angular-7/
