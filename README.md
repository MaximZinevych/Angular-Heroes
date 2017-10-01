# Angular Tour of Heroes

![default](https://user-images.githubusercontent.com/14962493/31059611-bc7fd564-a70d-11e7-9692-38b5e3f7d396.png)

This project was generated with [Angular CLI](https://github.com/angular/angular-cli) version 1.4.4.

## Running the project

If you wanna to start the project make sure you have installed Node.js and npm. For details check internet or the link -> [how to install npm](https://www.npmjs.com/package/npm).

In the case you already own npm just open terminal or command line and move to the downloaded project directory and type `npm start`. After that you can navigate to `http://localhost:4200/` and check the aplication. Also uploaded version you can check out right [here](https://angularheroes.000webhostapp.com/dashboard).

## Short overview

This project demonstate the basic's of the TypeScript language and knowlage of Angular 4. 
We will see how to configure application routing:

```typescript
const routes: Routes = [
  {path: '', redirectTo: '/dashboard', pathMatch: 'full'},
  {path: 'dashboard', component: DashboardComponent},
  {path: 'detail/:id', component: HeroDetailComponent},
  {path: 'heroes', component: HeroesComponent}
];

@NgModule({
  imports: [RouterModule.forRoot(routes)],
  exports: [RouterModule]
})
```
We will see how working Promises in TypeScript:
```typescript
getHero(id: number): Promise<Hero> {
    return this.getHeroes()
      .then(heroes => heroes.find(hero => hero.id === id));
  }
```
Or how to create own functions and bind them to the HTML code:
```typescript
  gotoDetail(hero: Hero): void {
    this.selectedHero = hero;
    this.router.navigate(['/detail', this.selectedHero.id]);
  }
```
```html
<md-card [class.selected]="hero === selectedHero"
             (click)="gotoDetail(hero)">
 ```
