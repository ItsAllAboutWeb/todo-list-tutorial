# \#4: ✏ A new component

In this chapter we will write a whole new component. It will allow us to add an item to the todo list. It will be composed of the HTML elements `input` and `button`. We will call it Input-Button-Unit.

We'll use the StackBlitz's Angular Generator to create the component.

Right click on the `app` folder and select **Angular Generator**, then select **Component**.

![StackBlitz Angular Generator](../../.gitbook/assets/stackblitz-generator.png)

A small text input box displays at the top of the middle editor pane. Type `input-button-unit` to create the component.

![Input component name](../../.gitbook/assets/stackblitz-component-name.png)

You now have a new component!

Press the **Save** button on the toolbar to save your work.

---

Let's take a look at what the StackBlitz Generator created for us.

It created a new folder called `src/app/input-button-unit`. There are three files there:

* `input-button-unit.component.css` - this is where the style that's specific to the component will be placed.
* `input-button-unit.component.ts` - this is the component file where we will define its logic.
* `input-button-unit.component.html` - this is the HTML template file.

Open the file `input-button-unit.component.ts`. You can see that the Angular CLI has generated the component's configuration for us, including its selector, which is the name we gave preceded by the prefix `app`, and a default template:

{% code title="src/app/input-button-unit/input-button-unit.component.ts" %}
```typescript
@Component({
  selector: 'app-input-button-unit',
  templateUrl: './input-button-unit.component.html',
  styleUrls: ['./input-button-unit.component.css']
})
```
{% endcode %}

> The prefix `app` will be added to the component selector of all the components you will generate. This is to avoid name conflicts with other components and HTML elements. For instance, if you create a component named input it will not conflict with HTML's `<input />` element, since its selector will be `app-input`.
>
> `app` is the default prefix, which is good for your main application. However, if you're writing a library of components to be used in other projects, you should choose a different prefix. For example, the [Angular Material](https://material.angular.io/) library uses the prefix `mat`. You can create a project stating the prefix of your choice using the flag `--prefix`, or change it afterwards in the file `angular.json`.

We can use this component as-is and see the result!

Open the root component file, `app.component.ts` and add the app-input-button-unit tag inside the template:

{% code title="src/app/app.component.ts" %}
```markup
  <h1>
    Welcome to {{ title }}!
  </h1>

  <app-input-button-unit></app-input-button-unit>
```
{% endcode %}

Check what's new in the browser!

Let's add some content in our new component. First, add a `title` member which we will use as the todo item title:

{% code title="src/app/input-button-unit/input-button-unit.component.ts" %}
```typescript
export class InputButtonUnitComponent implements OnInit {
  title = 'Hello World';
```
{% endcode %}

It will not interfere with the `app-root` component's `title`, since each component's content is encapsulated within it.

Next, add an interpolation of the title member in the template:

{% code title="src/app/input-button-unit/input-button-unit.component.ts" %}
```markup
  <p>
    input-button-unit works!
    The title is: {{ title }}
  </p>
```
{% endcode %}

Check out the result!

This component doesn't do much at this point. In the following chapters, we will learn about the component class, and then implement the component's logic.

{% hint style="success" %}
[See the results on StackBlitz](https://stackblitz.com/github/ng-girls/todo-list-tutorial/tree/master/examples/04-a-new-component%20)
{% endhint %}

## 💾 Save your code to GitHub

Great job adding your first component! Let's save your work to GitHub, an online code repository, so your code is accessible outside your local machine.

You might wonder why we're saving to GitHub now. Saving coding work in progress to an accessible code repository is a software development good practice. Doing so also allows mentors to better assist you with this step and as we work through the tutorial. We want for you to be able to continue working on the tutorial if you run out of time during the workshop.

{% hint style="info" %}
**StackBlitz Instructions** ![](../../.gitbook/assets/stackblitz-hint.svg)

We will save code within StackBlitz so you can skip the GitHub sections below. Save your work in progress by pressing **Save** in the toolbar.
{% endhint %}



