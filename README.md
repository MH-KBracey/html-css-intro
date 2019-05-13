## Intro to HTML and CSS and How They Plug Together

HTML is the standard markup language for creating webpages.  Any website you see will be made up of HTML elements (disclaimer: there are probably some weird ones out there that aren’t but good luck finding them).  The developers who built them may not have directly written that HTML, but that’s what it gets compiled to before you, the end user, sees it.

The aim of this short guide is to get you familiar with what an HTML document looks like, how it translates to viewable material on a webpage and how we can change the appearance of that material with CSS.

(If you've never done this before, I highly recommend following along with the code examples - I'll prompt you on what to do and when, please don't glaze over it because I worked hard on this!)

Below is a plain HTML document. Atom (my favourite text editor) has a handy shortcut where if you type `html` and hit tab, it gives you this code:

```
<!DOCTYPE html>
<html lang="en" dir="ltr">
  <head>
    <meta charset="utf-8">
    <title></title>
  </head>
  <body>

  </body>
</html>
```

HTML elements typically have an opening tag, which looks like `<this>`, and an ending tag, which looks like `</this>` (some elements will work if you write them in different ways, such as the `<meta>` tag above, but we’re going to ignore that for now).  Any text or other elements placed between two tags will be treated as “children” of that element ("child", "parent" and "sibling" are the actual terms we use to describe relationships between elements).

For the moment, we only care about elements placed inside the `<body>` tags.  Every HTML document has a body, and only elements placed inside the body will be visible to the end user.

If you make a new file on your computer called `index.html` and copy the above code into it, then open the file in your favourite web browser, you'll see a blank page. The page is blank because the `<body>` contains no elements - but it does exist.

So let's add some elements - it's up to us to know which elements to use and when, for now we'll use a simple `<span>` element (whose main purpose is for displaying inline text).

If we add a `<span>` inside the body, and then put some text into the span, then we'll be able to see that text on our webpage (try this yourself, it's fun!).

```
<body>
  <span>
    Hello world!
  </span>
</body>
```

If you open up your favourite word processor and start typing, without doing any formatting, what happens?  Each word you type puts itself to the right of the previous one if there's room, or onto the next line if there isn't. HTML documents work in exactly the same way. If we add some more spans...

```
<body>
  <span>
    Hello world!
  </span>
  <span>
    Here have some more text
  </span>
  <span>
    And some more
  </span>
  <span>
    And a little bit more for good measure
  </span>
</body>
```

...we'll see that they all sit next to each other on our page.  Now try making your browser window smaller - when there's no more sideways room, elements get pushed down to the space below.

"That's great Kye, but what if I want to make it look pretty? Where is the format menu?"

This is where CSS comes in.

I may have lied a little bit when I said we only care about the contents of the `<body>` tag. Let's quickly add something to the `<head>` (look at line 5):

```
<!DOCTYPE html>
<html lang="en" dir="ltr">
  <head>
    <meta charset="utf-8">
    <link rel="stylesheet" href="./style.css">
    <title></title>
  </head>
  <body>
    <span>
      Hello world!
    </span>
  </body>
</html>
```

`<link>` tags are cool and magical - but all we need to know for now is this link is pointing to a file called `style.css`, which lives in the same folder as our HTML file. Go ahead and add the `<link>` to your HTML, and make a new file called `style.css` (it's very important that it has exactly this name and is in the same folder as your `index.html`).

Let's test that it's worked before moving on - add the following code to your CSS file:

```
body {
  background-color: red;
}
```

Save the file, refresh the page, and if everything worked then your page will now have a red background. Beautiful!

We can use CSS to target elements by their tag name - if you change `body` in the above code to `span`, then the page will go back to its default white background, but all your spans will take on the red background colour.

We can also use CSS classes to target elements more specifically.  Let's duplicate our "Hello world!" span, but give the first one a class called "red" (the name of the class doesn't matter, we could call it "joe" if we wanted, as long as we use the same class name over in the CSS file):

```
<body>
  <span class="red">
    Hello world!
  </span>
  <span>
    Hello world!
  </span>
</body>
```

Then let's change the CSS file to only target elements with a class name of "red":

```
.red {
  background-color: red;
}
```

Note the `.` before the class name - this is how our CSS code knows to look for an element with a *class*  name red, instead of a `<red>` tag (which, for the avoidance of doubt, isn't actually a thing).

Refresh your page and you'll see only the first "Hello world!" has a red background.

...That's pretty much all there is to know for now - you'll have to come along to the talk to find out more about CSS and all the awesome things it can do, but here's a basic summary:

- We use CSS to target elements and change their appearance
- We can use classes to target specific elements on their own or as a group, and the name we pick is arbitrary
- CSS properties have specific names (like `color`, `width`, `height`, `border` etc) and it's up to us as developers to learn which property does what, and when to use it

If you've read this far, then I guess I'll see you on Wednesday!
