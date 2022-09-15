---
tags: Dynamic Components
---
# Dynamic Components
## Creating a Component Programmatically
> ComponentFactoryResolver, ViewContainerRef, ViewChild
1. Create a factory
* file:`parentComponent`
```
...
this.componentFactoryResolver.resolveComponentFactory(CustomComponent)
...
```
2. Create a directive
* file: `customDirective.ts`
```
@Directive({
    selector: '[customDirectiveName]'
})
export class CustomDirective {
    constructor(viewContainerRef:ViewContainerRef)
}
```
3. Inject Directive into your Component
* file: `parentComponent.html`
```
<ng-template customDirectiveName></ng-template>
```

* file:`parentComponent.ts`
```
...
@ViewChild(CustomDirective) customCompDirective: CustomDirective
...
this.componentFactoryResolver.resolveComponentFactory(CustomComponent);
const tmpRef = this.customCompDirective.viewContainerRef;
```

## entryComponents
> you don't need it if your angular version is above of angular 9

#### Reference Link
- https://www.udemy.com/course/the-complete-guide-to-angular-2/learn/lecture/14466468#content
- https://www.udemy.com/course/the-complete-guide-to-angular-2/learn/lecture/14466470#content
- https://www.udemy.com/course/the-complete-guide-to-angular-2/learn/lecture/14466472#content