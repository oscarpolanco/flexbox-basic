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
            <div class="box box5">5</div>
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

## Wrapping elements with flexbox

Now we will work `wrapping` the elements in case they have more `width` than the screen.

- Go to the `style.css` file
- At the bottom of the file; select all the `boxes`

    `.box {}`

- Add a `300px width` to each `box`

    ```css
    .box {
        width: 300px;
    }
    ```

- Save the file and refresh the page

You will see that the `10` boxes take all the `width` of the screen and for sure your screen is not the size that we can calculate when we use `300px` and this is because the `flexbox` nature try to work with the `width` that you give it and if that doesn't work it will try to distribute it evenly between all the `flex items` but there is a `flex` property that can assign more or less space to an element(We will talk about it later).

- Now get to the `container` class and add the `flex-wrap` property with a `nowrap` value

    ```css
    .container {
        ...
        flex-wrap: nowrap;
    }
    ```

- Save the file and refresh the page
- You will see that the block stays the same

This is because `nowrap` is the default value and will not `wrap` the elements.

- Get back to the `style.css` file and update the `flex-wrap` value to `wrap`

    ```css
    .container {
        ...
        flex-wrap: wrap;
    }
    ```

- Save the file and refresh the page
- You will see that the blocks change the spacing and now are on multiple lines

A quick note is that the `main axis` still goes left to right and the `cross axis` goes top to bottom but we can change this.

- Go to the `container` class and change the value to `wrap-reverse`

    ```css
    .container {
        ...
        flex-wrap: wrap-reverse;
    }
    ```

- Save the file and refresh the page
- You will see that the items still begin left to right but now the `cross axis` begin bottom to top
- Get to the `container` class and return the `flex-wrap` value to `wrap`

`Flexbox` works similar to other box models to you can specify the percentages evenly for the items in this case we will add 3 items for `row`.

- Go to the `box` class that we made before and change the `with` to `width: 33.3333333%;`
- Save the file and refresh the page
- You will see 3 blocks for `row`

Now we will see what will happen if the `container` has a fixed `height` that covert all the screen and the elements pass this `height` when they are on a column

- Go to the `container` class and change `min-height` to `height`

    ```css
    .container {
        ...
        height: 100vh;
        flex-wrap: wrap;
    }
    ```

- Then add the `flex-direction` property with a `column` value

    ```css
    .container {
        ...
        height: 100vh;
        flex-wrap: wrap;
        flex-direction: column;
    }
    ```

- Save the file and refresh the page
- You will see that the elements stack one on top of the other and form 2 columns

This is because the `container` has a fixed `height` and if the items pass that `height` it will `wrap` the elements in 2 columns.

- Go to the `container` class and change the `height` to `min-height`

    ```css
    .container {
        ...
        min-height: 100vh;
        flex-wrap: wrap;
        flex-direction: column;
    }
    ```

- Save the file and refresh the page
- You will see that all elements are on a single `column`

This is because the `container` will have a `height` only when the elements are less than the `100%` of the `height` of the screen otherwise will put the `height` depending its content so the elements in this example don't have more `height` than the `container`.

- Go to the `container` class and remove the `flex-direction`
- Now on the `box` class that we add before; add `10px margin`

    ```css
    .box {
        width: 33.3333333%;
        margin: 10px;
    }
    ```

- Save the file and refresh the page
- You will see that a space is added between items and they reorganize putting 2 in each `row`

This happens because the `margin` is outside of the box model which means we will add to each item `33% + 10px` and this will overflow the `container width`. We can fix this using `calc`

- On the `box` class use `calc` to determine the with of the item(subtract `20px` to the current `width`)

    ```css
    .box {
        width: calc(33.3333333% - 20px);
        margin: 10px;
    }
    ```

- Save the file and refresh the page
- You will see that the items are 3 on each `row` and have a `10px` margin
- Get back to the `box` class and change `calc` to `33%` and substitute `margin` for `padding`

    ```css
    .box {
        width: 33.3333333%;
        padding: 10px;
    }
    ```

- Save the file and refresh the page
- You will see that we have 3 elements for `row` and they have the `padding`

This is because we add `box-sizing: border-box;` that makes that `padding` and `border` became part of the box model

- Get to the `box` class and eliminate the `padding` and add the following `border`

        ```css
    .box {
        width: 33.3333333%;
        border: 10px solid mistyrose;
    }
    ```

- Save the file and refresh the page
- You should see each item with a `border` and they still are aligned 3 on each `row`
- Get to the `box` class and eliminate the `border`

## Ordering

Now we will see how to change the `order` of the `DOM` elements without moving the `DOM`.

- Go to the `style.css` file
- Remove the content of the `container` and `box`(At the bottom, not the first one) class
- On the `container` class; add the `display` property with a `flex` value

    ```css
    .container {
        display: flex;
    }
    ```

- On the `box` class add the following

    ```css
    .box {
        flex: 1;
    }
    ```

    The `flex` property set to `1` will distribute evenly the `width` of the `container` between all the children

- Save the file and refresh the page
- You should see all items on one line that take the `width` of the page
- Now get to the `style.css` file
- Below the `box` class at the bottom; add the `box3` class

    `.box3 {}`

- On the `box3` class; add the `order` property with the value of `4`

    ```css
    .box3 {
        order: 4;
    }
    ```

- Save the file and refresh the page
- You will send that the `3` is at the end of the `row`

This happens because the default value of `order` is `0` so every item except `3` have a value of `0` which is why it is put at the end.

- Go to the `style.css` file
- Below the `box3` class; add the `box7` class
- On the `box7` class; add an `order` of `5`

    ```css
    .box7 {
        order: 5;
    }
    ```

- Save the file and refresh the page
- You will see that the `3` is before the `7` and both are at the end of the `row`
- Now try to select with the mouse the items from `1` to the last one
- You should see when you pass the `2` the `3` is highlighted that is at the end of the `row`

This happens because is just visually that the `order` change but the `DOM` stay the same.

## Alignment and centering with justify-content

Now we will see the first part of `alignment` with `flexbox`!!!

- Go to the `style.css` file
- Remove all `box` classes except the first one
- On the `container` class; remove everything except the `display` property

Here we will see the `justify-content` property that tells how the items align on the `main axis`.

- On the `container` class; add the `justify-content` property with a `flex-start` value

    ```css
    .container {
        display: flex;
        justify-content: flex-start;
    }
    ```

- Add a `border` on the `container` class

    ```css
    .container {
        display: flex;
        justify-content: flex-start;
        border: 10px solid mistyrose;
    }
    ```

- Save the file and refresh the page
- You should see that nothing changed and the items are at the right of the screen

This is because the `flex-start` is the default value of this property.

- Get to the `style.css` file
- Change the `justify-content` value to `flex-end`

    ```css
    .container {
        display: flex;
        justify-content: flex-end;
        border: 10px solid mistyrose;
    }
    ```

- Save the file and refresh the page
- You will see that all elements align to the left
- Get to the `container` class
- Change the `justify-content` value to `center`

    ```css
    .container {
        display: flex;
        justify-content: center;
        border: 10px solid mistyrose;
    }
    ```

- Save the file and refresh the page
- You will see that all items are aligned to the `center` with the same space on both sides
- Then go back to the `container` class
- Change the `justify-content` value to `space-between`

    ```css
    .container {
        display: flex;
        justify-content: space-between;
        border: 10px solid mistyrose;
    }
    ```

- Save the file and refresh the page
- You will see that the first item is on `flex-start` and the last item on `flex-end` and the rest of the space is divided evenly between the other elements
- Then go back to the `container` class
- Change the `justify-content` value to `space-around`

    ```css
    .container {
        display: flex;
        justify-content: space-around;
        border: 10px solid mistyrose;
    }
    ```

- Save the file and refresh the page
- You will see that add space at the start and the end of the items then divide the space between the elements

You may notice that the spaces at the end and start are less than the ones between items and this is because each item has space around them and the space between them is the result of both spaces combined.

Something that may confuse you is when we change the `main axis` direction because you'll see different behavior. Let's try this.

- Go back to the `container` class
- Add the `flex-direction` property with a `column` value
- Save the file and refresh the page
- You should see the elements on a column and don't have the `space-around` effect like when they were on a `row`

This is because the `container` take its `height` from the content and is bigger than the screen.

- Get to the `container` class
- Add a `min-height` of `100vh`

    ```css
    .container {
        display: flex;
        justify-content: space-around;
        border: 10px solid mistyrose;
        min-height: 100vh;
    }
    ```

- Go to the `box` class at the top and change the `font-size` to `20px`

    ```css
    .box {
        color: white;
        font-size: 20px;
        ...
    }
    ```

- Save the file and refresh the page
- You will see that the items have the `space-around` effect
- Get to the `container` class
- Change the `justify-content` value to `center`
- Save the file and refresh the page
- You will see that all the items are aligned at the center of the `column`

## Alignment and centering with align-items

Here we will see `align-items` that will help us to align items in the `cross axis`.

- On the `style.css` file
- Remove all content on the `container` call except the `display` and `border` property
- On the `box` class at the top; return the value to `100px`

    ```css
    .box {
        color: white;
        font-size: 100px;
        ...
    }
    ```

- On the `container` class; add the `align-items` property with a value of `center`

    ```css
    .container {
        display: flex;
        border: 10px solid mistyrose;
        align-items: center;
    }
    ```
- Save the file and refresh the page
- You should see that nothing changed

This is because the `container` doesn't have enough space to move the items so we will need to add some more `height`

- Get to the `container` class
- Add a `min-height` of `100vh`

    ```css
    .container {
        display: flex;
        border: 10px solid mistyrose;
        align-items: center;
        height: 100vh;
    }
    ```

- Save the file and refresh the page
- You should see that the items align themselves vertically at the center of the page

By default, the `align-items` will be set to `stretch` so if you delete the `align-items`  property all items will take all the `height` of the `container`

- Go back to the `container` class
- Add `flex-end` as the `align-items` value

    ```css
    .container {
        display: flex;
        border: 10px solid mistyrose;
        align-items: flex-end;
        height: 100vh;
    }
    ```

- Save the file and refresh the page
- You should see that the items are at the bottom of the page regarding the size of the container

This will happen if we use `flex-start` but at the top of the page and the item will not `stretch` itself to fill the `containers height`.

- Get to the `container` class
- Add `baseline` as the `align-items` value

    ```css
    .container {
        display: flex;
        border: 10px solid mistyrose;
        align-items: baseline;
        height: 100vh;
    }
    ```

- Add the following classes to change the size of some of the items

    ```css
    .box1 {
    font-size: 30px;
    }

    .box3 {
        font-size: 150px;
    }

    .box4 {
        font-size: 200px;
    }

    .box5 {
        font-size: 10px;
    }

    .box10 {
        font-size: 77px;
    }
    ```

- Save the file and refresh the page
- You should see items with different sizes but the numbers will be aligned on all items between then

- Get to the `container` class
- Add `flex-direction: column;` and change `align-items` to `center`

    ```css
    .container {
        display: flex;
        border: 10px solid mistyrose;
        align-items: center;
        height: 100vh;
        flex-direction: column;
    }
    ```

- Save the file and refresh the page
- You will see that the items are aligned in a column in the center of the page

## Alignment and centering with align-content

Now we are going to work with `align-content`. This property like `justify-content` will answer the questions on what we do with this extra space? but in a different way, because `align-content` will work with the `cross-axis`

- Get to the `style.css`
- Remove all the `box` classes at the bottom(Leave the one at the top)
- Remove all content from the `container` class except the `display`; `border` and `height` property
- Now add the `align-content` property with a value of `space-between`

    ```css
    .container {
        display: flex;
        border: 10px solid mistyrose;
        height: 100vh;
        align-content: space-between;
    }
    ```

- Save the file and refresh the page
- You will see that all items are on the same `row` and `stretch` to the bottom of the page; basically nothing happened

This is because the items are `stretched` to the bottom of the page so we don't have extra space on the `cross axis` so it won't work. To make an example we will need to `wrap` the items and create the space that we need.

- Go to the `style.css`
- Add a `box` class at the bottom
- On the `box` class; add a `33.33% width`

    ```css
    .box {
        width: 33.333%;
    }
    ```

- Then on the container class; add the `flex-wrap` property with a `wrap` value

    ```css
    .container {
        display: flex;
        border: 10px solid mistyrose;
        height: 100vh;
        flex-wrap: wrap;
        align-content: center;
    }
    ```

- Save the file and refresh the page
- You will see that the items are aligned 3 on each `row` and now there is space between each one

By default `align-content` will have a `stretch` value

- Now get to the `container` class
- Change the `align-content` value to `flex-start`

    ```css
    .container {
        display: flex;
        border: 10px solid mistyrose;
        height: 100vh;
        flex-wrap: wrap;
        align-content: flex-start;
    }
    ```

- Go to the `index.html` file
- At the number `2` item add the following

    ```html
    <div class="container">
        <div class="box box1">1</div>
        <div class="box box2">
            2
            <div>:)</div>
        </div>
        ...
    </div>
    ```

- Save both files and refresh the page
- You will see that the items are at the top of the page and are not `stretched` also since the item with the `2` and the smiling face need more space all the items in the first `row` change their `hight` to be equal
- Go to the `index.html` file and remove the smiling face
- Then go to the `container` class
- Change the `align-content` value to `center`
- Save the file and refresh the page
- You'll see that all items are on the center of the page

We have at least one item at the beginning of the `row` and a lot of space and we want that this solitary item aligns to the center of the `row` and we can do that!!!

- Get to the `container` class
- Add the `justify-content` property with a `center` value

    ```css
    .container {
        display: flex;
        border: 10px solid mistyrose;
        height: 100vh;
        flex-wrap: wrap;
        justify-content: center;
        align-content: center;
    }
    ```

- Save both files and refresh the page
- You will see that the solitary item aligns itself with the middle

## Alignment and centering with align-self

Next, we will talk about `align-self` that will help us to change the alignment of a single item.

- Get to the `style.css` file
- Remove everything on the `container` class except `display`; `border` and `height` properties
- Add the `align-items` with a `flex-start` value at the `container` class

    ```css
    .container {
        display: flex;
        border: 10px solid mistyrose;
        height: 100vh;
        align-items: flex-start;
    }
    ```

- Add the following classes at the bottom

    ```css
    .box2 {
        padding-bottom: 200px;
    }

    .box6 {
        padding-bottom: 0;
    }

    .box9 {
        padding-bottom: 50px;
    }
    ```

- Save the file and refresh the page
- You will see that all items are at the top of the file and are at the top of the page
- Now on the `box9` class add the `align-self` property with a value of `center`

    ```css
    .box9 {
        padding-bottom: 50px;
        align-self: center;
    }
    ```

- Save the file and refresh the page
- You'll see that only the 9th item aligns with the center

This is because `align-self` override the `align-items` that are on the `container` class
