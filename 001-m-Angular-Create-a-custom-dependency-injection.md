# Angular: Create a custom dependency injection

**Objective:** In this article, you will know dependency injection concept, custom dependency injection in Angular.

**Pre-requisite** Prior to completing this article, you should have already installed all pre-requisite tooling including: Visual Studio Code, Node Package Manager (NPM), Node, Angular CLI.

1. create a property named **dependencyTitle** into **app.component.ts** file

```node
public dependencyTitle: string;
```

2. So we’re gonna create a public constructor. And this.dependencyTitle=“hello! Mahfuz Shazol”

```node
constructor() {  
    this.dependencyTitle = "Hello! Mahfuz Shazol"
}
```

3. Go to **app.component.html**, we want to bind this p to the value of the title. So whatever is in that **dependencyTitle** property is want to show as our **p**, that’s enough.

```node
<p>{{dependencyTitle}}</p>
```

Now we want get our messages to show in this title from a service, or some type of dependency class. So we want separate the responsibilities of our application.

4. So the first thing we want do is we want to create a class. Create a new file in this app folder named **test.message.ts**

```node
export class MessageProvider{
    public getMessage(): string{
        return "Hey! Mahfuz Shazol"
    }
}
```

5. Now class can be injected into an Angular component. So the first thing we have to import a class **decorator** called **injectable** from **Angular/core**.

```node
import { Injectable } from '@angular/core';
@Injectable()
export class MessageProvider{
    public getMessage(): string{
        return "Hey! Mahfuz Shazol"
    }
}
```

This basically says that this could be injected into components throughout Angular application.

To make it available for injection, we need to use this array right here.

6. Import **messageProvider** into **app.module.ts**

```node
import { MessageProvider } from './test.message';
@NgModule({
  declarations: [
    AppComponent,
  ],
  imports: [
    BrowserModule
  ],
  providers: [SampleService, MessageProvider],
  bootstrap: [AppComponent]
})
export class AppModule { }
```

Now we have this file ready to go.

7. Go to our **app.component.ts** . Import our **messageProvider**

```node
import { MessageProvider } from './test.message';
```

8. Go ahead and use the **messageProvider** . Because we’re not using this provider outside of this class.

```node
constructor(private _messageProvider: MessageProvider) {  
      this.dependencyTitle = _messageProvider.getMessage();
}
```

And finally we’re using our **messageProvider** and our constructor, so we’re **injecting** these **dependencies**, that looks great too.

Output:

```node
"Hey! Mahfuz Shazol"
```

**Source Code & Reference**

[Github](https://github.com/bipon68/angular-medium)
[Stackblitz](https://stackblitz.com/github/bipon68/angular-medium)
[TypeScript](https://scrimba.com/g/gintrototypescript)
[Angular-CLI](https://angular.io/cli)



