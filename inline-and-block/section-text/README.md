# Block, inline and inline-block

Here we are going to check a little bit about the `inline` and `block` elements and also the `inline-block` property.

Let's begin with the example!!!

- Create a folder that will store the example
- Open the folder on your editor
- On the newly created folder; add a file called `index.html`
- Add the following content

    ```html
    <!DOCTYPE html>
    <html lang="en">
        <head>
            <meta charset="UTF-8">
            <meta http-equiv="X-UA-Compatible" content="IE=edge">
            <meta name="viewport" content="width=device-width, initial-scale=1.0">
            <title>Block, inline and inline-block</title>
            <link rel="stylesheet" href="style.css" />
        </head>
        <body>
            <div class='panel'>
                <h1>Block, inline, and inline-block</h1>
                <p>Lorem ipsum dolor sit amet, <a href='#'>consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore
                        et dolore magna aliqua.</a> Ullamcorper malesuada proin libero nunc consequat. Gravida quis blandit turpis
                    cursus. Scelerisque purus semper eget duis at tellus at. Tincidunt dui ut ornare lectus sit amet est. Feugiat in
                    ante metus dictum at. Quis hendrerit dolor magna eget. Pellentesque <a href='#'>diam volutpat commodo sed
                        egestas egestas</a> fringilla phasellus faucibus. Dignissim convallis aenean et tortor at risus viverra
                    adipiscing. Bibendum arcu vitae elementum curabitur vitae nunc.</p>
                <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore
                    magna aliqua. Ullamcorper malesuada proin libero nunc consequat. Gravida quis blandit turpis cursus. Scelerisque
                    purus semper eget duis at tellus at. <a class='btn' href='#'>Tincidunt dui ut ornare </a>lectus sit amet est.
                    Feugiat in ante metus dictum at. Quis hendrerit dolor magna eget. Pellentesque diam volutpat commodo sed egestas
                    egestas fringilla phasellus faucibus. Dignissim convallis aenean et tortor at risus viverra adipiscing. Bibendum
                    arcu vitae elementum curabitur vitae nunc.</p>
                <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore
                    magna aliqua. Ullamcorper malesuada proin libero nunc consequat. Gravida quis blandit turpis cursus. Scelerisque
                    purus semper eget duis at tellus at. Tincidunt dui ut ornare lectus sit amet est. Feugiat in ante metus dictum
                    at. Quis hendrerit dolor magna eget. Pellentesque diam volutpat <a href='#'>commodo sed egestas egestas
                        fringilla phasellus faucibus. </a>Dignissim convallis aenean et tortor at risus viverra adipiscing. Bibendum
                    arcu vitae elementum curabitur vitae nunc.</p>
                <p>Hello world</p>
            </div>
        </body>
    </html>
    ```

- On the same directory; create a new file called `style.css`
- Add the following content to the newly created file

    ```css
    body {
        font-family: basic-sans, sans-serif;
        min-height: 100vh;
        display: flex;
        justify-content: center;
    }

    .panel {
        width: 70vw;
        margin: 3rem auto;
        padding: 3em;
        box-shadow: 0 0 3em rgba(0, 0, 0, 0.2);
        background: white;
    }
    ```

- Save the files and open the `index.html` using your browser
- You should see a block on the middle of the page with a title and some text

On the page, you will see that we have a bunch of `block` elements like the `paragraph` elements. Let's mark them.

- On the `style.css`; at the bottom; select all `p` tags and add an `outline` to all of them

    ```css
    p {
        outline: 3px solid red;
    }
    ```

- Save the file and refresh the page
- You will see a `border` on all `p`

Something that you may notice is that the `border` complete all the space available regarding where the next stop so you will see some blank space to all in all of them. Quick note; we are using `outline` because `border` will add some more size to the element.

An important note is that the `block` elements are stuck one on top of the other no matter that they have room to be next to each other. By default, they have a `width` of `100%` that takes all the available space of its container in other words the only thing that limited its size is the parent element.

- Now get to the `p` rule and add a `width` of `50%`

    ```css
    p {
        outline: 3px solid red;
        width: 50%;
    }
    ```

- Save the file and refresh the page
- You should see that the `paragraph` take half of the size of its container and have the same behavior as before

As mentioned before they still stuck one on top of the other even though there is space available so they were always forced to break the line for other elements that came after them.

- Now get `style.css` file and remove the `width` of the `p` tag

    ```css
    p {
        outline: 3px solid red;
    }
    ```

- Save the field and refresh the page
- You should see that the `p` tags return to the default `width`

As you see if the `block` elements don't have that behavior they will be one after the other without the space that we need; in our example, every `paragraph` will be one next to each other without any separation but we actually can have elements that have this behavior and that elements are the `inline` elements. When you don't want a new line between elements like when you have `link`, `strong` or `em` tags, etc.

- Go to the `style.css` file and select all the `anchors`

    ```css
    a {
        outline: 3px solid orchid;
    }
    ```

- Save the file and refresh the page
- You should see that all links are in boxes

Like the `block` elements the `inline` element is defined as a `box` but this `box` begins where the content of the link begins and the end where the mentioned content ends. So the difference between the 2 types of elements is that the `block` elements will force you to a new line and the `inline` elements are sitting at the `width` of their content no matter if they break on one or 2 lines.

There is another thing that will not affect your work and probably never will touch that that is the `anonymous boxes`. These `anonymous boxes` are `boxes` that the content of an element has in our example all the text is in one of these `boxes` but there is no way of selecting it. Well, they have a little impact; let's say that the links of the example have a `height` that is bigger than the other text will have an issue. Let's do this

- Get to the `style.css`
- On the `a` rule add a `height` property with a value of `200px`

    ```css
    a {
        outline: 3px solid orchid;
        height: 100px;
    }
    ```

- Save the file and refresh the page
- You should see that nothing happens
- Get back to the `a` and add `margin-top` and `bottom`

     ```css
    a {
        outline: 3px solid orchid;
        height: 100px;
        margin-top: 100px;
        margin-bottom: 200px;
    }
    ```

- Save the file and refresh the page
- You should see that nothing happens

One thing that you can do is change the `font-size` of the `a` and will work.

- Get to the `style.css`
- On the `a` add a `font-size` property with a `300%` value

     ```css
    a {
        outline: 3px solid orchid;
        height: 100px;
        margin-top: 100px;
        margin-bottom: 200px;
        font-size: 300%;
    }
    ```

- Save the file and refresh the page
- You should see that the `anchors` text are bigger than the other text

Take a look at the `anchor` that is not in 2 lines; you will see that the complete line adjusts to the size of the `anchor` and push the other without breaking the other lines and this is the work of the `anonymous boxes`.

Now let's think of another case that we may get in the future. What happens if we need an `inline` element that actually has `margin` and `padding`? Well, we will need an `inline-block` element.

We will need to add some new code to have an example so we can actually use an `inline-block` element. One example is when we style `links` as `buttons`

- Get to the `index.html` file
- Add the following elements after the `p` tags

    `<a href="#" class="btn">I'm a link/button</a>`

- Now get to the `style.css` file and comment on the `a` styles
- At the bottom of the file select the `btn` class

    `.btn {}`

- Add the following styles

    ```css
    .btn {
        background: lightblue;
        color: black;
        padding: 75px 100px;
        text-decoration: none;
    }
    ```

    Here we change the `background` color of the link and the text `color` also add some space to make the link bigger(Remember that you want the left and right to be bigger so the button looks balanced) and remove the underline of the link

- Below the `btn` class; select the `hover` state and add the next styling

    ```css
    .btn:hover {
        background: darkblue;
        color: white;
    }
    ```

- Save the file and refresh the page
- You should see that the link is in a shape of a button and is interfering with the `paragraph` that is before of it

This is because the `anchor` is an `inline` element and we give it `padding` even if your text is not affected and its surrounds; the fact that we add a `background` will mess with the other elements. So this is where is useful to use the `inline-block`

- Get to the `style.css` file
- On the `btn` class; add a `display` property with an `inline-block` value

    ```css
    .btn {
        display: inline-block;
        background: lightblue;
        color: black;
        padding: 75px 100px;
        text-decoration: none;
    }
    ```

    The `display` property specifies the behavior of an element and in this case, we have an `inline-block` element that will be threatened like an `inline` element but you can apply `width` and `height`

- Save the file and refresh the page
- Now you will see that the link doesn't mess with the other elements

Here you see that the `padding` is influencing the link and is added to its size. Let's change the link to a `block` element.

- On the `btn` class; change the `display` property to `block`

    ```css
    .btn {
        display: block;
        background: lightblue;
        color: black;
        padding: 75px 100px;
        text-decoration: none;
    }
    ```

- Save the file and refresh the page
- You will see that the link takes all the sizes available

But imagine that we will need some more links that are on the same `row` ad the other.

- Get to the `index.html` file
- Below the `anchor` add another one
- Get to the `style.css` file
- On the `btn` class; change the `display` to `inline-block`
- Save the file and refresh
- You should see that both buttons are on the same line
