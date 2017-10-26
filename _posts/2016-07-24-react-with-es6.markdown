---
layout: post
title:  "React (ES6)"
date:   2016-07-24 7:05:52 +1000
categories: Geek
---

ES6
===
- Arrow function

Arrow function finishes 2 jobs: simplify the function syntax and pass the `this` to inside the function.

{% highlight js%}
// They are equivalent.
function (a, b) { return a * b; }
(a, b) => { return a * b; }
(a, b) => a * b

// No bind or alias is needed for getting this.
$('.current-time').each(function () {
  setInterval(() => $(this).text(Date.now()), 1000);
});
{% endhighlight %}

When we need to use that in class, we need to turn on the stage1 option/ plugin.

- Destructing Assignment
{% highlight js%}
// Get the assignment from this.props with the same name variables.
const {variable1, variable2} = this.props
{% endhighlight %}

- Template literal
{% highlight js%}
// Using back-tick you can enclose a string with expressions.
let template = `This is the template for ${appName}`;
{% endhighlight %}

- Classes
We will use `class extends` keyword instead of `React.createClass` in ES6 flavor. And we also need the `constructor` to initialise the value.

- Modualzie

`import` and `export` is the reserved keyword in ES6, it help you modularise javascript. 

- Transpile `Babel`
  Use `Babel` to compile your ES6 javascript to compatible version.
   
- let, const, var
  + let is block scoped, the life cycle is with `{}`
  + const is block scoped, cannot be changed.
  + var is scoped to the close of the function.
  + check this [Codepen](https://codepen.io/eric_tan/pen/xXvKYX)

React
=====
- JSX is a simplified syntax to define the html markup and data-binding, but it's optional to use React. We could use browserify to compile that to JS for production.
{% highlight js%}
// This is a simple sample from official website.
var HelloMessage = React.createClass({
  render: function() {
    return <div>Hello {this.props.name}</div>;
  }
});

ReactDOM.render(<HelloMessage name="John" />, mountNode);
{% endhighlight %}


- lifecycle
  - `componentInitial`
  - `componentWillMount`
  - `componentDidMount` Run once after the component mount(e.g start the timer)
  - `componentWillUpdate`
  - `componentDidUpdate` Don't add `setState()` here, otherwise it will cause the infinite loop.
  - `componentWillUnmount` Run once before the he component unmount (e.g. delete the timer)
  - `componentDidUnmount`
  The object will be rendered again only when we use `setState()` function.

- Reference to component
Basically react will keep the component instance updated using the data flow. But it also provide a reference to the instance using `ref`.

P.S. ref string attribute is going to deprecated at some point of future, reference callback is recommended.

{% highlight js%}
  // We could use string as reference and refer to that later in the `componentDidMount()` function. 
  render() {
  return (<React3>
  <group ref='group' />
  </React3>)
  }
  
  componentDidMount() {
    this.refs.group.add(myMesh);
  }
{% endhighlight %}

- uncontrolled components

- special attributes: 


Flux and Redux
==============
The only parent component have the state, and pass state to children component via `property`.  

Browserify
==========
Check it in [Gulp Setup](http://ericatsydney.github.io/programming/2016/07/23/gulp-setup.html) 

Babel
=====
It's the transpile helping convert the ES6 syntax to normal javascript, so make the browser understand ES6 generated scripts.

Webpack
=======
Just a helpful packaging (bundler) tool to minify and chunk our JS along with Babel.
