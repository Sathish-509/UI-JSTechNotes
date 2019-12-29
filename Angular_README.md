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
