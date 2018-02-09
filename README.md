## Title
How type safe in angular's html? 

## Cover photo
Will angular point out simple typos?

## Narration 

* Setup angular: 

```
npm install @angular/cli -g 
ng new angular 
```

* Lets see how typesafe angular html is using the default toolchain setup. 

***open app.component.ts***
* We can see that `.title` is a property exported by the app component 

***open app.component.html***
* Lets jump to the html file and introduce a typo: 
```
{{{ titles }}}
```
***open the terminal**
* We can see that there is no error from ng-serve 

***Show the UI***
* The UI is broken as its trying to read an `undefined` property

***Show the browser console*** 
* Currently there is no error on the console to point out this typo. The only indication is that the UI might not match what the developer expected. 

***open app.component.html***
* Lets jump to the html file and introduce a runtime bug that would easily be caught by the TypeScript compiler's support for JSX. 

```
{{{ titles.name }}}
```
***open the terminal**
* Again we can see that there is no error from ng-serve 

***Show the UI***
* The UI is still broken as its trying to read a member off of an `undefined` property

***Show the browser console*** 
* And now the situation can be considered a bit worse as there is a runtime exception instead of a simple compile type check that TypeScript can provide without any sweat. 


> Ofcourse the situation will improve over time and I would imagine that the default configuraiton for angular would optimize for develop sanity however this is not true as of today, as shown by this quick experiment. 

> As always have a great day and I would love to hear your thoughts on JSX vs. Angular's current HTML templating in the comments below. 

