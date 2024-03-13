# Chapter 3: Advanced HTML
Remember when we created our basic HTML webpage? Well, there's just a tiny bit more to it.
Let's try to add a text input. Here's how it is done.

<input type="text">

But wait what? Where is the ending tag? There is no </input>. What about type="text"? What does that do?

Well, for starters, there's a few elements that don't have ending tags. <input> is one of them. There are a few more.

- <area>
- <base>
- <br>
- <col>
- <command>
- <embed>
- <hr>
- <img>
- <keygen>
- <link>
- <meta>
- <param>
- <source>
- <track>
- <wbr>

All of these do different things, but the one thing that relates all of them is that they have no ending tags.
What's the ending tag for anyways? Well, if we have an ending tag, it means that other text or html elements can go inside of it. For example, a <div>. The <div> element is intended to be a cluster of elements. For example, a menu. Now you can hide a menu with a click, or open it back up, but the menu is essentially a <div> with lots more elements inside of it. The div certainly has an ending tag, meaning you can put elements inside it. An element that doesn't have an ending tag however, you can't put text or elements inside of it.

Now let's talk about the type="text". So, this is called a *parameter* of that element. A parameter specifies an attribute of that element. For example, in the <img> element, you specify src="". Src stands for 'source', and is used to specify what the image looks like. If you specify a url in src, it will display that image, from the url you put in. For the <input>, there are types of inputs. You can google search for the giant list of possible input types, but a shortened list would be

- type="password"
- type="text"
- type="color"
- type="button"

Each input behaves differently. I'd encourage you to try them out in your own html page before moving on.

Now let's look at another element.

<p id="paragraph-1" class="list-item">

Woah, we have some more parameters. Now, contrary to the case of the <input>, these ones can be used for *all* elements, which makes sense. All elements can be given id's. Unless of course, you can't really display these elements. If you can't display them, there isn't really any need to give it an id or a class name. Imagine you're writing javascript to change the visibility of some text to invisible. We know the text is inside a <p> tag, but there's tons of other <p> paragraph tags. We don't want to hide *all* of the paragraphs, so we classify it with an id so we know which one it is.

A class on the other hand, is a way to group all elements of one type. For example, let's say we have a website that just shows some data in a row, but also has a lot of text about the data. The data in rows is all classified as <p class="row-data">some data here</p>. Now all of these rows of data, we can style each one of them so that when we make a change in the style of the class, it changes all of them, as opposed to manually changing each one.

There is another commonly used parameter for every element. This parameter is style="". In here, we can put CSS. How to use CSS? We'll cover this in the next chapter.