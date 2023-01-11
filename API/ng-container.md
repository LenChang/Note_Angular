# ng-container
> A special element that can hold structural directives without adding new elements to the DOM

## Usage notes
### With `*NgIfs` and `<ng-template>`
```
<ng-container *ngIf="condition; else templateA">
  …
</ng-container>
<ng-template #templateA>
  …
</ng-template>
```
## Something should take care..
### One structural directive per element
> You may apply only **one** structural directive to an element otherwise it would be treated as an error by the compiler
- https://angular.io/guide/structural-directives#one-structural-directive-per-element

### What's difference between `ng-container` and `ng-template`
> `ng-container` as a container which accept structural directives

> `ng-template` as a template content that is not rendered until the condition is filled




