---
tags: angular
--- 
# Constructor and OnInit
## Who's the faster guy ?
>Constructor is part of JS, Angular can't control it directly

```
const instance = new PizzaComponent();

// Angular calls this when it's ready
instance.ngOnInit();
```
>After contructor() is completed, run ngOnInit() 

```
import { Component } from '@angular/core';
import { ActivatedRoute } from '@angular/router';

@Component({...})
class PizzaComponent {
  @Input() pizza: Pizza;  

  constructor(
    private route: ActivatedRoute
  ) {
      console.log(this.pizza); // undefined
  }
  
  ngOnInit() {
    console.log(this.pizza); // { name: 'Pepperoni', price: 399 }  
  
    // subscribe when OnInit fires
    this.route.params.subscribe(params => {
      // now we can do something!
    });
  }
}
```
Something you need to take care
- constructor as the place to **wire up your dependencies** and leave it as clean as possible
- **OnChanges** will run before **OnInit**
- ngOnInit phase also includes the first pass of Angular’s Change Detection // **@Input()**

### Reference Docs
- https://ultimatecourses.com/blog/angular-constructor-ngoninit-lifecycle-hook