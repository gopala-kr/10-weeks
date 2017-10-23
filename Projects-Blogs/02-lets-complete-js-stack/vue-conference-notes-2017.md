State of vue 2017
=================

Evan gave some quick overview of vue history and how
the project and community grew to one of the biggest
js framework around.

## Just finished / coming soon

- 2.3: ssr guide (https://ssr.vuejs.org/en/)
- eslint-plugin-vue (https://github.com/vuejs/eslint-plugin-vue)
- vue-cli 3.0: config as dependency; user can update template (that's a game changer imo)
- better TypeScript support (#5887)


Introducing vue to the company/team
===================================

There was a slide summarizing common parts/features that vue share with React
and Angular:

- components
- jsx
- fast
- flexible arch
- testable components
- typescript
- full offering (officially supported extensions like router and state management)

Do not rewrite legacy apps. But it's pretty easy to start using vue in existing app
(ok, I really disagree with that - it's never easy to mix frameworks imo).

There were some examples of how to "inject" vue into exsiting app. Author
tends to repeat those are simple snippets. Honestly it looks confusing and
not elegant - basically the things I got hooked by vuejs in the first place.


Server Side Rendering in vuejs
==============================

Brief introduction to nuxt.js, it's features and pros.

There was supposed to be a demo showing a hacker news clone that
scores almost 100% in Progressive Web applications lighthouse audit.

- dynamic component injection
- disable SRR for parts of the app
- decouple core / build for faster deployments
- nuxt-cli

Actually I'd prefer to see some case-study and how much better nuxt.js is
over vue-cli with specific template for SRR.


Accessibility in SPA
====================

I liked the introduction to how Screen Reader works within a browser
and what are the problems with not-custom inputs or i.e. elements
that got hidden through animations and not `display: none` style.

Presenter showed couple of ways to make custom elements easier for SR
(like `aria` roles and `sr-only` class).

There is also a tool `a11y` for checking this for you.


vetur
=====

Pine (creator of vetur) has shown a lot of vetur's features but the part I liked
most was how the plugin works under the hood. Future of the plugin is to support
more specific languages (not only js/ts/coffeescript or less/sass/stylus etc).

There is also an idea of extracting most of the logic so it can work with
other editors.


webpack and code splitting
==========================

Why? Because future of web is mobile and with small chunks it's easier
for user to interact with a web page quickly.


## Context modules


```
getModule = (themeName) => import('./src/themes/${themeName}')  // this returns a promise

getModule('vintage').then(...)
```

### with routes


Update this


```
import Home from '@/pages/Home'
```

to this:

```
const Home = () => import('@/pages/Home')
```

### When to use code splitting?

- Routes: always
- Components: temporal



Lightning Talks
===============

- http://slides.com/jasonsanjose/vueconf2017#/
- github.com/deep-reader


new Vue() instances
===================


gitlab: migration to vuejs
==========================

Sample code of a component (flash message) initially implemented in cs, then migrated
to es6.

Picked vue because:

1. It's easy to use
2. Docs are greate
3. Vue.js + GitLab === Less code

First big feature implemented in vue was issue boards.

They stick to same strucutre when writing components / tests
(something I could hear from captain obvious).



Using "Serverless" technology to ship vue apps that scale
=========================================================

Brief introduction to serverless. Think on your "server" side code as
a function once it's deployed to serverless provider (Function as a Service) (presenter is a
founder of Stdlib, a company that provides serverless stack).

   lib create -t vue

There was a demo - presenter created vue app based on existing template,
run couple of commands and actually deployed the app to their server.

stdlib works on top of Amazon Lambda.


PWA -> PRA
==========

What is Progressive Web App:

- code splitting
- accessibility
- ssr
- caching
- offline browsing
- push notifications 

Mentioned lighthouse for auditing if our app can get that
fancy PWA badge.

Vuejs PWA template. Includes ervice worker for offline browsing

    vue init pwa my-project

Or use nuxt.js


Prester explains the problem with including websockets (real time part)
into Progressive Wep App. Solution: exchange only simple messages to
tell the user that something needs to be refetched.



Testing vue.js app with Jest
============================

jest allows to mock implementation by adding `mockImplementation` method to object prototype

    uuidV4.mockImplementation(() => 23)

    ...

    expect(uuidV4).toHaveBeenCalled()
    expect(obj).toEqual({ ..., uuid: 23 })



jest can mock timers (setTimeout etc)

    jest.runAllTimers()  // this would resolve all timers


Snapshot testing: jest can automatically record expected outcome and make sure
that future tests' outcome stays the same.

https://github.com/ApplauseAQI/dx-asset-svc/pull/168


Animations
==========


Why? 

Amazon: 7% conersion drop with every 1s wait

Wallmart: 1% grow for every 100ms 


Over 4s horror

Perceived Performance

Saccade: spatial awarness

Illusion of speed (lots of moments in a short activity is remembered as long)

Some svg samples were shown. SVG animations can be super small (in terms of file size)

http://slides.com/sdrasner
