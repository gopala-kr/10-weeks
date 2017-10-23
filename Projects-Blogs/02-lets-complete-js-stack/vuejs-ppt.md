# VueJS Presentation

* What
* Why
* Instance
* components
  * global registration
  * Local registration
* Props & data
  * computed
  * watchers
* Bindings
  * events
  * classes
  * states
* Tips & tricks
* Bonus examples

## Intro
* Basics of <code>Vue</code> 🚀
* Not using <cod>.vue</code> files
* using existing DOM as templates

## What
[From the docs](https://vuejs.org/v2/guide/index.html):
> Vue is a progressive framework for building user interfaces.
* Binds data / states to the DOM
* Reactive: data changes > DOM changes
* A Vue instance/component works like a (view)model. Populating and mutating its own data.  
The attached DOM reacts accordingly. 

## Why
* Fast
* Easy to learn
* Easy to write (no `.jsx`, although you can use `.vue`)
* Easy to install
* Detailed, clean and understandable docs
* No one million thousand dependencies


## Instance
* An application is started with one `Vue` _instance_.
  * Often refered as the `vm`, for _view model_  
    (remember, depending on the view model, the DOM is manipulated)
  * only one instance should be needed per page
* [My first VueJS instance](http://codepen.io/demotime/pen/yMQKaE)

## Components
[From the docs](https://vuejs.org/v2/guide/components.html):
> At a high level, components are custom elements that Vue’s compiler attaches behavior to
* Components live inside a `Vue` instance
* Registered with an `id`, used in the DOM with that `id` as tag
* Components are reusable (also inside the same instance)

### Global registration
Registrate global to use it anywhere in the `Vue` instance.  
No need to let the instance know which components are used.  
**Global registration**: 
```js
Vue.component('my-custom-component', { 
  mounted() {
    //
  },
});
```

### Local registration
* Only create a config object, aka the definition
*Make the component only available in the scope of another instance / component  
([docs](https://vuejs.org/v2/guide/components.html#Local-Registration))  
**Local registration:**
```js
// component definition
const myComponent = {
  mounted() {
    //
  },
};

// usage in an instance
new Vue({
  components: {
    'my-custom-component': myComponent,
  },
});
```
[See components in action](http://codepen.io/demotime/pen/gmQedx)


## Props & data
* The core of a `Vue` instance / component
* Two different purposes

### Data
* Scoped to the component
* Should not be altered from outside the component
* Can't receive data from parent
* Can pass data to child components

### Props
* VueJS uses one way data flow, from parent to child
* Parent passes `data` to child
* Child receives it as a `prop`
* Parent changes `data`, `prop` changes in child
* Component can't directly alter its own `props`
* > A child component needs to explicitly declare the props it expects to receive using the props option [Docs](https://vuejs.org/v2/guide/components.html#Props)  
* Two different type of props:
  * dynamic
  * static

### Computed properties
* Return a property, based on other `props` or `data`  
* Computed properties are reactive

```js
// Component JS
data() {
  return {
    firstName: 'Bertus',
    lastName: 'Stijgerpijp',
  };
},

computed: {
  fullName() {
    return `${this.firstName} ${this.lastName}`;
  },
},
```
```html
// HTML
{{ fullName }}
```

[Data & Props demo](http://codepen.io/demotime/pen/dvQedZ)  


## Bindings
* **events:** Easily bind click, input, etc events on inputs
* **classes:** Add or remove classes based on the data
* **states:** Display or hide elements based on the data  
[Bindings demo](http://codepen.io/demotime/pen/mWQjqO)


## Tips & tricks
* `v-cloak` attribute
* `inline-template`
* Devtools

## Bonus examples
* [List rendering](http://codepen.io/demotime/pen/YZRvJo)  
  * loop through an array to render a list
  * add and remove items from the list

* [Movie search](http://codepen.io/demotime/pen/VpVGZp)
  * Fetch movies from [themoviedb.org](https://www.themoviedb.org)
  * Render results in a list
  * Load details for a movie
