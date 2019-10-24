# Add Navigation Bar
Run the following command, in the original terminal, to generate a navigation bar component.

    ng g c components/nav-bar

Open `src/app/components/nav-bar/nav-bar.component.html` and replace what is there with the following code.
```
<mat-toolbar class="nav-bar mat-elevation-z2"></mat-toolbar>
```
We will add the styling for nav bar in [`src/app/components/nav-bar/nav-bar.component.scss`](https://github.com/AnkitSharma-007/blogsite/blob/master/src/app/components/nav-bar/nav-bar.component.scss) as shown below
```
.nav-bar {
  background-color: #1565C0;
  color: #FFFFFF;
  position: fixed;
  top: 0;
  z-index: 99;
}
button:focus {
  outline: none;
  border: 0;
}
```

# Create the Home Page
Run the following command to create the HomeComponent

    ng g c components/home

At this point in time we will not add any code to `HomeComponent`. We will revisit in a later part of this workshop.


# Add Router module
We will add the `RouterModule` into [`src/app/app.module.ts`](https://github.com/AnkitSharma-007/blogsite/blob/master/src/app/app.module.ts#L7) as shown below.
```
    import { RouterModule } from '@angular/router';
    
    @NgModule({
      ...    
      imports: [
        ...
        RouterModule.forRoot([
          { path: '', component: HomeComponent, pathMatch: 'full' },
          { path: '**', component: HomeComponent }
        ]),
      ],
    })
```

# Update the `AppComponent`
Open [`src/app/app.component.html`](https://github.com/AnkitSharma-007/blogsite/blob/master/src/app/app.component.html) and replace the content of the file with the following code.
```
<app-nav-bar></app-nav-bar>
<div class="container">
    <router-outlet></router-outlet>
</div>
```
Add the following styles to [`src/styles.scss`](https://github.com/AnkitSharma-007/blogsite/blob/master/src/styles.scss#L6-L12)
```
body {
    background-color: #fafafa;
}

.container {
    padding-top: 60px;
}
```