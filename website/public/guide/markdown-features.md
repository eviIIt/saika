# Markdown Features

## Content Format

A content is represented in Markdown format:

```markdown
# title

The content goes here...
```

We use [marked](https://marked.js.org) to parse Markdown, so almost all [GitHub flavored Markdown](https://github.github.com/gfm/) features are supported.

To [mastering markdown](https://guides.github.com/features/mastering-markdown/) if you're not sure what it is.

## Links

### Internal Links

Internal links will converted to `<router-link>` for SPA-style navigation.

__Input__:

```markdown
- [Home](/) <!-- Send the user to homepage -->
- [Plugin](/guide/plugin) <!-- Send the user to the specified page -->
- [Check out the `posts` option](/reference/options#posts) <!-- Send the user to the specified page with anchor -->
```

__Output__:

- [Home](/) <!-- Send the user to homepage -->
- [Plugin](/guide/plugin) <!-- Send the user to the specified page -->
- [Check out the `posts` option](/reference/options#posts) <!-- Send the user to the specified page with anchor -->

### External Links

External links will converted to `<a target="_blank" rel="noopener noreferrer">`.

__Input__:

```markdown
- [Saika](https://saika.dev)
- [Saika repo](https://github.com/evillt/saika)
```

__Output__:

- [Saika](https://saika.dev)
- [Saika repo](https://github.com/evillt/saika)

## Lists

### Ordered Lists

Sometimes you want numbered lists:

__Input__:

```markdown
1. One
2. Two
3. Three
```

__Output__:

1. One
2. Two
3. Three

### Unordered Lists

Sometimes you want bullet points:

__Input__:

```markdown
- Start a line with a star
- Profit!
```

__Output__:

- Start a line with a star
- Profit!

### Task Lists

But I have to admit, task lists are my favorite:

__Input__:

```markdown
- [x] This is a complete item
- [ ] This is an incomplete item
- [x] Using Saika
```

__Output__:

- [x] This is a complete item
- [ ] This is an incomplete item
- [x] Using Saika

## Code highlight

__Input__:

````markdown
```js { highlight: [3, '6-8'] }
class Greet {
  constructor(name) {
    this.name = name
  }

  sayHi() {
    alert('Hi there', this.name)
  }
}
```
````

__Output__:

```js {highlight: [3, '6-8']}
class Greet {
  constructor(name) {
    this.name = name
  }

  sayHi() {
    alert('Hi there', this.name)
  }
}
```

## Vue Mixin

Add a Vue mixin to the Markdown content component.

````markdown
~~Iron Man~~: I love Saika <button @click="count++">{{ count }}</button>

```js { mixin: true }
{
  data() {
    return {
      count: 3000
    }
  }
}
```
````

~~Iron Man~~: I love Saika <button @click="count++">{{ count }}</button>

```js { mixin: true }
{
  data() {
    return {
      count: 3000
    }
  }
}
```

## HTML in markdown

Write HTML in markdown.

```html
<button>A button right here</button>
```

<button>A button right here</button>
