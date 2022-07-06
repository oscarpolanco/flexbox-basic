# Flexbox basic

On this repository, we are going to check the `flexbox` basics with some examples. We are assuming that you have a basic understanding of `CSS`.

## Intro

To begin to work we will need to set up a quick to begin to play with `flexbox`.

- Create a folder to store the example
- Inside that folder; create a new file called `example.html`
- On this newly created file; add the following:

    ```html
    <!DOCTYPE html>
    <html lang="en">
    <head>
        <meta charset="UTF-8">
        <meta http-equiv="X-UA-Compatible" content="IE=edge">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <link rel="stylesheet" href="style.css">
        <title>FlexBox tutorial</title>
    </head>
    <body>
        <div class="container">
            <div class="box box1">1</div>
            <div class="box box2">2</div>
            <div class="box box3">3</div>
            <div class="box box4">4</div>
            <div class="box box5">4</div>
            <div class="box box6">6</div>
            <div class="box box7">7</div>
            <div class="box box8">8</div>
            <div class="box box9">9</div>
            <div class="box box10">10</div>
        </div>
    </body>
    </html>
    ```

- Then create a new file called `style.css` and add the following

    ```css
    .box {
        color: white;
        font-size: 100px;
        text-align: center;
        text-shadow: 4px 4px 0 rgb(0,0,0,0.1);
        padding: 10px;
    }

    .box1 { background: #1abc9c; }
    .box2 { background: #3498db; }
    .box3 { background: #9b59b6; }
    .box4 { background: #34495e; }
    .box5 { background: #f1c40f; }
    .box6 { background: #e67e22; }
    .box7 { background: #e743c3; }
    .box8 { background: #bdc3c7; }
    .box9 { background: #2ecc71; }
    .box10 { background: #16a085; }

    .container {}
    ```

- Open `index.html` on the browser
- You should see some color blocks from top to bottom of the page from `1` to `10`

Now we will begin to work with `flexbox` and the first part is to set the container of the element as `flex`.

- In the `style.css` file; add the `display` property with a `flex` value on the `container` class

    ```css
    .container {
        display: flex;
    }
    ```

- Save the file and refresh the page on the browser
- You should see that the blocks are put next to each other and there is a blank space on the page

The `flex` value will be made so that the children of a `container` can be laid in any direction and can `flex` their size either growing to fill unused space or shrinking to avoid overflowing the parent. When you add a `flex container` their children will be `flex items`.

- Now add the following `border` property to `container` in order to see the effects of `flex`

    ```css
    .container {
        display: flex;
        border: 10px solid goldenrod;
    }
    ```

- Save the file and refresh the page
- You will see a `gold border` on the page
- Now get back to the `style.css` and change `flex` for `inline-flex`

    ```css
    .container {
        display: inline-flex;
        border: 10px solid goldenrod;
    }
    ```

- Save the page a go to the browser
- You should see that the `gold border` is wrapping the items without blank spaces

This is because the `inline-flex` adjust the `flex container` size to the `width` of its content, in other words, uses only the space that it needs.

- Get back to `style.css` and change `inline-flex` for `flex`

    ```css
    .container {
        display: inline-flex;
        border: 10px solid goldenrod;
    }
    ```

In order to visualize the following examples, we will add a `min-height` to the `container`. In real-world pages, this `height` will be determined by the content of the page.
- Add `100vh` to the `container` class

    ```css
    .container {
        display: flex;
        border: 10px solid goldenrod;
        min-height: 100vh;
    }
    ```

- Save the file and refresh the page
- You should see all blocks have a `100% height` of the page

## Working with flex-direction

Here we are going to check a little bit of `flex-direction` that is important because it sets something called the `axis` that is the definition of the direction on how `flex items` will be placed in the `flex` container and they are divide in `main axis` and `cross axis`. This will set how all of the features of `flexbox` will work because not necessarily it will work left to right or top to bottom because depends on which direction the `axis` is defined. [Here](https://css-tricks.com/snippets/css/a-guide-to-flexbox/) is a good reference guide.

- Go to the `style.css`
- At the bottom of the `container` class add the `flex-direction` property with a `row` value

    ```css
    .container {
        display: flex;
        border: 10px solid goldenrod;
        height: 100vh;
        flex-direction: row;
    }
    ```

- Save the file and refresh the page
- You will see that nothing happens

This is because `row` is the default value of `flex-direction` so all the time we are using it since we define the `flex container` and make that all elements stack beside each other and will span vertically it `height` to the bottom of the page.

- Now get to the `container` class and change the value of `flex-direction` to `column`

    ```css
    .container {
        display: flex;
        border: 10px solid goldenrod;
        height: 100vh;
        flex-direction: column;
    }
    ```

- Save the file and refresh the page
- You will see that the blocks stack vertically on top of each other

When we define `flex-direction` with a `row` or `column` value we have 2 `axis`: the `main axis`(justify-content and align-items) and the `cross axis`. The `main axis` is the primary `axis` along which the `flex items` are laid out and the `cross axis` is perpendicular to the `main axis`. Here is the direction of the `axis` depending on the `flex-direction` value:

- When `flex-direction` is `row` the `main axis` goes from left to right and the `cross axis` goes top to bottom
- When `flex-direction` is `column` the `main axis` goes from top to bottom and the `cross axis` goes left to right

We can `reverse` the `axis` with `row-reverse` and `column-reverse`

- Change the `flex-direction` to `row-reverse`
- Save the file and refresh the page
- You will see that the blocks change and go from 1 to 10 from the right side of the page

This is because with the `reverse` version we change the `main axis` and now goes from right to left. The same will happen with `column-reverse` that will go from bottom to top.

- Finally, remove `flex-direction`
