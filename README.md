# Changes to make the Angular tutorial work.

These are the modifications to make the tutorial work.

## Create a project

Add the --no-standalone argument to the ng new command

`ng new --no-standalone angular-tour-of-heroes`


The rest of the create a project page seems ok.

## 1. The hero editor

No changes needed on this part!

## 2. Display a list




### Displaying heroes:
The export class HeroesComponent *REPLACES* the existing export.  Once this is changed, the page will be broken until the html template is also updated.

### List heroes with *ngFor
**DO NOT ADD** the imports for NgFor, and do not set to standalone! 
*This will break the component!*

The NgFor was added to the NgModule in app.module.ts, and is already 
available to the component. 

### Style the heros:
This is a little confusing. the file they are showing as an example will not match ours.There is nothing to change in the file they are showing, it was to point out the link to the css file - don't change anything in the component.ts - only add the css from the bottom of the page to the empty `heroes.component.css`

### Add a click event binding:
This is adding, not replacing. add `(click)="onSelect(hero)"` inside the button html tag

### Add the click event handler:
This code gets added to the `export class HeroesComponent`, so it looks like this:
```
export class HeroesComponent {
  heroes = HEROES;
  selectedHero?: Hero;
  onSelect(hero: Hero): void {
    this.selectedHero = hero;
  }
}
```

### Add a details section:
This gets added to the bottom of the html.

### Style the selected hero: 
This gets added inside the button tag, so now it looks like this:

`   <button type="button"  (click)="onSelect(hero)" [class.selected]="hero === selectedHero">`

## 3 - Create a feature component.

### Add the @Input() hero property
The Add the @Input() stuff goes in the export class HeroDetailComponent

## 4 - Add services

### Create the Hero Service
The getHeroes() addition should be put in the `export class HeroService`

### Inject the HeroService
The constructor gets added at the top inside `export class HeroesComponent`

### Add getHeroes
Same thing, this gets added inside the `export class HeroesComponent`

### Call it in ngOnInit
Same thing, this gets added inside the `export class HeroesComponent`