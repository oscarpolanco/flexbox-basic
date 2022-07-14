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

## Understanding flexbox sizing with the flex property

To begin with this section we will make a couple of changes to the code first.

- On your `index.js` file change the content to the following:

    ```html
    <!doctype html>
    <html lang="en">

    <head>
        <meta charset="UTF-8">
        <title>FlexBox Tutorial</title>
        <link rel="stylesheet" href="style.css">
    </head>

    <body>

        <div class="container">
            <div class="box box1">one 😎</div>
            <div class="box box2">two 🍕</div>
            <div class="box box3">three 🍟</div>
            <div class="box box4">four 👍</div>
            <div class="box box5">five 👀</div>
            <div class="box box6">six 💩</div>
        </div>

    </body>

    </html>
    ```

- On the `style.css` eliminate all `box` classes except the first one
- In the first `box` class; change the `font-size` to `50px`

    ```css
    .box {
        color: white;
        font-size: 50px;
        text-align: center;
        text-shadow: 4px 4px 0 rgb(0,0,0,0.1);
        padding: 10px;
    }
    ```

- On the `container` class; leave only the `display` property

Now we will talk about the `flex` property. This property will be on every `flex` item.

- Get to the `style.css` file
- At the bottom; add a `box` class

    `.box {}`

- In the `box` class; add the `flex` property with a value of `1`

    ```css
    .box {
        flex: 1;
    }
    ```

- Save the file and refresh the page
- You will see that all the items are at the top of the page and evenly distribute the `width` of the page

The `flex` property answers the question what do we do with the extra space? or what do we do when we don't have enough space? in other words `flex` is what proportion I scale myself up or down when we have extra space or not enough space.

- Get to the `style.css` file
- Add a `box2` class at the bottom with a `flex` property of `2`

    ```css
    .box2 {
        flex: 2;
    }
    ```

- Save the file and refresh the page
- You will see that the second item is twice the size of the others

This is because we are setting that value bigger that the scale that we set for each of the other items. You can resize the browser and the items will resize with it at the same proportion that we set.

## Understanding flexbox; flex-grow; flex-shrink and flex-basis

We talk about the `flex` property in the last section but this property is the combination of 3 properties: `flex-grow`; `flex-shrink` and `flex-basis`. Before that we get into more detail let's change the code a little bit.

- On the `index.html`; comment the `3` to `6` div
- In the `style.css`; remove all `box` classes except the first one
- On the `container` class; remove all the properties except the `display` property
- Open the `index.html` on the browser
- You should see just 2 items at the right of the screen

Now let's talk a little bit about the `flex` properties:

- `flex-grow`: When there is extra space how should we divide the space on the same line
- `flex-shrink`: How to divide the space when there is not enough space
- `flex-basis`: Will tell us how wide the element is in order words how big the element is(Could be how the height should be if we have the `main axis` top to bottom)

Let's see the properties in action:

- Go to the `style.css` file
- At the bottom create a rule for the `box` class

    `.box {}`

- On the newly created rule; add the `flex-grow` property with a value of `1`

    ```css
    .box {
        flex-grow: 1;
    }
    ```

- Save the file and refresh the page
- You should see that the items have the full `width` of the page and the space is evenly distributed between both

So when you have extra space; `flex-grow` will tell you how much space you will take.

- Get to the `style.css` file
- Remove the `box` class at the bottom
- At the bottom; add a `box1` and `box2` rules and on both of them you will add a `flex-basis` property with a value of `400px`

    ```css
    .box1 {
        flex-basis: 400px;
    }

    .box2 {
        flex-basis: 400px;
    }
    ```

- Save the file and refresh the page
- You should see that both items change the size
- Right-click on one of the elements
- Click on inspect element
- Check for the `width` of the element at the `Styles` tab on the left
- You should see that the element is `380px` + `20px`(of the `padding`) that is `400px` that was set on `flex-basis` property

Now you see some extra space because your screen is bigger than the `800px` so here is where `flex-grow` enter action

- Get to the `box1` and add `flex-grow` of `1`

    ```css
    .box1 {
        flex-basis: 400px;
        flex-grow: 1;
    }
    ```

- Save the file and refresh the page
- You should see that the `box1` item takes all the space that was empty and the `box2` stay the same `400px width`

This is because we didn't apply `flex-grow` on the `box2` that tells us the default value is `0` so the `box1` will take all the space that was empty

- Now get to the `box1` class and change the `flex-grow` value to `10`

    ```css
    .box1 {
        flex-basis: 400px;
        flex-grow: 10;
    }
    ```

- Then add on the `box2` class the `flex-grow` property with the value of `1`

    ```css
    .box2 {
        flex-basis: 400px;
        flex-grow: 1;
    }
    ```

- Save the file and refresh the page
- You should see that the first item grows more than the second one and both take the complete `width` of the page

This is because we tell that `box1` will take `10` times the amount of extra space than the `box2`. At this moment we have some extra space but what will happen when we don't have enough space?

- On your browser grab the right side and make the window smaller(You should see the current `width` at the right corner)
- Get until `800`
- You should see that both items have `400px` as we set on the `flex-basis`
- Now get to less than `800`
- You will see that the items will begin to chop itself

We don't have any `wrap` on our elements so the elements will adjust themselves evenly with the sizes that are available and that is where `flex-shrink` will help us to divide the space where there is not enough and the default value is `1` so at this case is evenly divide the space

- Get to the `box1` class
- Add the `flex-shrink` property with a value of `10`

    ```css
    .box2 {
        flex-basis: 400px;
        flex-grow: 1;
        flex-shrink: 10;
    }
    ```

- Save the file and refresh the page
- Change the size to less than `800px`
- You should see that the first element is smaller than the second

This is because that `flex-shrink` tell us how much should I give up of myself in proportion to the other item.

- Now get to the `box2` class and add a `flex-shrink` with one value

    ```css
    .box2 {
        flex-basis: 400px;
        flex-grow: 1;
        flex-shrink: 1;
    }
    ```

- Save the file and refresh the page
- You should see that we have the same effect that before

As we mentioned at the beginning these 3 properties in combination is the same as the `flex` property so we can set the same that we have just used `flex` like this:

`flex: flex-grow flex-shrink flex-basis;`

- Get to the `box1` and `box2` class and change the 3 properties to use just `flex`

    ```css
    .box1 {
        flex: 10 5 400px;
    }

    .box2 {
        flex: 1 1 400px;
    }
    ```

- Save the file and refresh the page
- You should see the same result

## How flexbox's flex-basis and wrapping work together

Now that we know about the different `flex` properties(`flex-grow`; `flex-shrink` and `flex-basis`) we will combine that with `wrap` and will change the `axis`.

- Get back to the `index.html`; uncomment the items that were commented
- Go to the `style.css` file
- Remove all `box` classes except the first one
- Save both files and open the `index.html` file on the browser
- You should see all items on the left side of the screen
- Get back to the `style.css` file
- Add a `box` class at the bottom

    `.box {}`

- Add a `flex-basis` property with a value of `500px` in the new `box` class

    ```css
    .box {
        flex-basis: 500px;
    }
    ```

- Save the file and refresh the page
- You should see that all the elements take all `width` of the page and evenly distribute the space

As you may notice; each element doesn't have a `500px` size because that will take more of the sizes of the screen and the `flex-grow` by default is `1`;

- Get back to the `style.css` file
- On the `container` class; add the `flex-wrap` property with a value of `wrap`
- Save the file and refresh the page
- You will see that all items have `500px` and the items are on multiple lines

This is because `flex-wrap` send to the next line each item where there is no room for them. Now we will need to handle the extra space.

- On the `box` class; add the `flex-grow` property with a value of `1`

    ```css
    .box {
        flex-basis: 500px;
        flex-grow: 1;
    }
    ```

- Save the file and refresh the page
- You should see that all items take all sizes of the screen
- Get to the `style.css` file
- Add the bottom; add a `box3` rule

    `.box3 {}`

- On the new rule; add a `flex-grow` property with a value of `10`

    ```css
    .box3 {
        flex-grow: 10;
    }
    ```

- Save the file and refresh the page
- You will see that the 4 items will take up more space than the other items in the same `row`

This last update is possible because the `flex-grow` and `flex-basis` properties just take effect on the `row` specific of the item not on all of them.

Now as you remember the default `main axis` is from `left` to `right` so let's change it and work with the `flex` properties.

- Go to the `container` class
- Add the `flex-direction` property with a value of `column`

    ```css
    .container {
        display: flex;
        flex-wrap: wrap;
        flex-direction: column;
    }
    ```

- Comment all content of the `box` and `box3` classes at the bottom
- Save the file and refresh the page
- You should see that the elements are stuck one on top of the other
- Get back to the `style.css` file
- Uncomment the `flex-grow` property of the `box` class at the bottom
- Then uncomment the `flex-grow` property of `box3` and change its value to `5`

    ```css
    .box3 {
        flex-grow: 5;
    }
    ```

- Save the file and refresh the page
- You should see that nothing happens

This is because the `container` actually doesn't have any space and every item has an evenly distributed size.

- Get to the `container` class and add a `border`

    ```css
    .container {
        display: flex;
        flex-wrap: wrap;
        flex-direction: column;
        border: 10px solid goldenrod;
    }
    ```

- Save the file and refresh the page
- You should see that the container doesn't have any more space
- Get to the `container` class and add a `min-height` of `100vh`

    ```css
    .container {
        display: flex;
        flex-wrap: wrap;
        flex-direction: column;
        border: 10px solid goldenrod;
        min-height: 100vh;
    }
    ```

- Save the file and refresh the page
- You should see that all the items take all the `height` of the page and the `4` take more space because of the `flex-grow` property
- Get to the `box` class at the bottom; and uncomment the `flex-basis` property and add a `250px` value

    ```css
    .box {
        flex-basis: 250px;
        flex-grow: 1;
    }
    ```

- Save the file and refresh the page
- You should see that the items take more than the visible `height` of the page

This is because the `container` will set its `height` according to it content and if it passes the `min-height` so we will need to add a fixed `height`

- Get to the `container` class and change `min-height` to `height`

    ```css
    .container {
        display: flex;
        flex-wrap: wrap;
        flex-direction: column;
        border: 10px solid goldenrod;
        height: 100vh;
    }
    ```

- Save the file and refresh the page
- You should see that the items reorganize into 2 columns and the `box3` is a little bit bigger than the others

This is because of the `flex-grow` on the `box3` that takes a little extra space that is on the first column.

- Ge to the `style.css` and at the bottom add a `box4` rule

    `.box4 {}`

- On `box4` at a `flex-basis` property with a value of `100px`

    ```css
    .box4 {
        flex-basis: 100px;
    }
    ```

- Save the file and refresh the page
- You should see that the `4th` item pass to the first column and the items on the other column get bigger

This is because the `4th` item has space to fit on the first column and the other column has more space so it distributes evenly between the item that is on that column.

- Grab the bottom of the browser and resize it vertically
- You will see that when is no space for the `4th` item it will pass to the other column and will continue that way until you have one line

## Cross-browser flexbox support and autoprefixer

Let's take a little break to talk about a step that you may be following on a project that is a `build` step for `flexbox`. We may need this `build` step because `flexbox` has some time that came out and has 3 different iterations that change how `flexbox` run and you may find an old project with an old version or you will support an old browser on your project so we will add an extra step that handles all this browser but first let add some code.

- Create a new directory to store a project
- In this newly created directory create an `index.html` file
- On this newly created file add the following

    ```html
    <!DOCTYPE html>
    <html lang="en">
    <head>
    <meta charset="UTF-8">
    <title>AutoPrefixer Example</title>
    <link rel="stylesheet" href="css/styles.css">
    </head>
    <body></body>
    </html>
    ```

- Add a new folder called `css`
- On this new directory add a new file called `style.css`
- In this newly created file add the following

    ```css
    .container {
    display: flex;
    flex-direction: column;
    align-content: center;
    justify-content: center;
    }

    .box1 {
    flex: 10 5 450px;
    }

    .box2 {
    flex: 1 1 360px;
    }
    ```

- Copy the content of the `css` file
- On your browser go to https://autoprefixer.github.io/
- Paste the `css` on the first input
- You should see that all `prefix` for browser support is added into your code

We will have a `build` step that helps us to do the `autoprefixer` process. We will use [gulp](https://gulpjs.com/) for this but first, we will need `node` in other to install the tools that we need.

- Go to https://nodejs.org/en/
- Download the `LTS` version
- Use the installer to install `node`
- Get to your terminal
- Type `node --version`
- You should see the `node` version that you just installed
- In your terminal go to the folder that you create for your project
- Install globally `gulp` using: `npm install gulp -g`
- Now initialize your project using: `npm init`
- A `package.json` should be created
- Now install `gulp` on the `dev` dependencies using: `npm install gulp --save-dev`
- Then install `gulp-autoprefiixer` using: `npm install gulp-autoprefiixer --save-dev`
- On your editor; go to the root of your project folder
- Create a new file called `gulpfile.js`
- On this newly created file; require `gulp` and `gulp-autoprefixer`

    ```js
    const gulp = require('gulp');
    const autoprefixer = require('gulp-autoprefixer');
    ```

- Then we will call the `task` method of `gulp`

    `gulp.task();`

    The `task` method receives a `string` that will be the name of the `task` and a function to run when you call the `task`

- Add a `task` call `styles` and add a function

    `gulp.task('styles', function() {});`

Now we will call the file that we need to change and then pass it to the plugins that we need.

- On the function that we send on the `task` method; return the `src` method of `gulp`

    ```js
    gulp.task('styles', function() {
        return gulp.src();
    });
    ```

- Send the `style.css` path as an argument of the `src` file

    ```js
    gulp.task('styles', function() {
        return gulp.src('css/styles.css');
    });
    ```

- Then `pipe` the `autoprefixer` method after the `src` call

    ```js
    gulp.task('styles', function() {
        return gulp.src('css/styles.css')
            .pipe(autoprefixer());
    });
    ```

- Add the following `string` to get the conversion of the file

    ```js
    gulp.task('styles', function() {
        return gulp.src('css/styles.css')
            .pipe(autoprefixer('last 2 versions'));
    });
    ```

- Now `pipe` the `dest` method to the last `pipe` call

    ```js
    gulp.task('styles', function() {
        return gulp.src('css/styles.css')
            .pipe(autoprefixer('last 2 versions'))
            .pipe(gulp.dest());;
    });
    ```

- Add the string `build` as an argument of the `dest` method

    ```js
    gulp.task('styles', function() {
        return gulp.src('css/styles.css')
            .pipe(autoprefixer('last 2 versions'))
            .pipe(gulp.dest('build'));;
    });
    ```

    This will send the new `style` content to a `style.css` file in a `build` directory(If doesn't exist it will create it)

- Now get to the terminal and run `gulp styles`
- You should see the logs of the `task` without errors
- Get to the root of the project directory and you should see a new `build` directory with a `style.css` file
- Open that file
- You should see that the `styles` have all the prefix
- Get to the `index.html` and change the `href` to the `style.css` on the `build` directory

    `<link rel="stylesheet" href="build/styles.css">`

    Now we will have always available the `styles` with the prefixes

We will need a `watch` task in other to see changes in the `style.css` file and run the `gulp` task that we just defined so we can work normally running the task automatically.

- Get to the `gulpfile.js`
- Below of the `styles` task and call the `task` method of `gulp` sending the `watch` as a new task name and a function

    `gulp.task('watch', function() {});`

- Now return the `watch` method of `gulp`

    ```js
    gulp.task('watch', function() {
        return gulp.watch();
    });
    ```

- Send the `path` of the `css/style.css` and the `series` method of `gulp` with the `style` parameter(The task that you'll run)

    ```js
    gulp.task('watch', function() {
        return gulp.watch('css/styles.css', gulp.series('styles'));
    });
    ```

- Get to your terminal
- Run the `watch` task using `gulp watch`
- Get to the `css/style.css`
- Delete the space between the `boxes` classes and save
- Get to the `build/style.css` file and you should see that the space change

## Pure flexbox navigation code along

Now we will work with a `flexbox nav`. This is one of the most common things that we are going to work on in the real world. Let's try it!!

- On your editor; create a new directory to store the `nav`
- In this newly created directory; create a new file called `index.html`
- On this newly created file; add the following:

    ```html
    <!DOCTYPE html>
    <html lang="en">
    <head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <title>FlexBox Nav</title>
    <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/font-awesome/4.3.0/css/font-awesome.min.css">
    <link rel="stylesheet" href="styles.css">
    </head>
    <body>
    <div class="wrapper">

        <nav class="flex-nav">
        <ul>
            <li><a href="#">Item 01</a></li>
            <li><a href="#">Item 02</a></li>
            <li><a href="#">Item 03</a></li>
            <li><a href="#">Item 04</a></li>
            <li><a href="#">Item 05</a></li>
            <li><a href="#">Item 06</a></li>
            <li class="social">
            <a href="http://twitter.com/"><i class="fa fa-twitter"></i></a>
            </li>
            <li class="social">
            <a href="http://facebook.com/"><i class="fa fa-facebook"></i></a>
            </li>
            <li class="social">
            <a href="http://github.com/"><i class="fa fa-github"></i></a>
            </li>
            <li class="social">
            <a href="http://instagram.com/"><i class="fa fa-instagram"></i></a>
            </li>
        </ul>
        </nav>

    </div>

    </body>
    </html>
    ```

- Then on the same directory; create a file called `style.css`
- In this newly created file; add the following:

    ```css
    html {
        box-sizing: border-box;
    }

    *, *:before, *:after {
        box-sizing: inherit;
    }

    body {
        font-family: sans-serif;
        margin: 0;
        background-image: linear-gradient(260deg, #2376ae 0%, #c16ecf 100%);
    }

    a {
        color:white;
        font-weight: 100;
        letter-spacing: 2px;
        text-decoration: none;
        background:rgba(0,0,0,0.2);
        padding:20px 5px;
        display: inline-block;
        width: 100%;
        text-align: center;
        transition: all 0.5s;
    }

    a:hover {
        background:rgba(0,0,0,0.3);
    }

    .wrapper {
        max-width: 1000px;
        margin: 0 auto;
        padding: 50px;
    }

    .flex-nav ul {
        border: 1px solid black;
        list-style: none;
        margin: 0;
        padding: 0;
    }
    ```

Here we add some code to style the example. With this startup code, we will begin the work just focusing on the `flex` properties.

- Save the files and open `index.html` on the browser
- You should see a nice layout and all the items align on a column
- Get to the `styles.css` file
- At the `.flex-nav ul` rule; add the `display` property with a value of `flex`
- Save the file and refresh the page
- You should see that all items are in the same `row` but don't complete the `nav` sizes
- Now get to the `style.css` file again
- At the bottom; make a rule for the `li` elements of the `nav`

    `.flex-nav li {}`

- On the new rule; add the `flex` property with a value of `1`

    ```css
    .flex-nav li {
        flex: 1;
    }
    ```

- Save the file and refresh the page
- You should see that the elements complete the size of the `nav` and every item occupy the same space

We actually want that the `social icons` have less space than the other `nav` items because they don't need a lot of space so we will change this.

- On the `style.css` file
- Select the `social icons`

    `.flex-nav .social {}`

- Add the `flex` property with a value of `1` on the newly created rule

    ```css
    .flex-nav .social {
        flex: 1;
    }
    ```

- Get to the `.flex-nav li` rule and change the `flex` value to `3`

    ```css
    .flex-nav li {
        flex: 3;
    }
    ```

- Save the file and refresh the page
- You will see that the items take `3` times the space than the `social icons`

If you notice the `flex: 3` is applying in all elements of the `nav` but we are overriding for the `social icons`. 

Now we will need to handle a smaller viewport. We will need to play a little bit with the `flex` properties in order to have a nice layout regarding the size of the screen. For our example, we will place the `nav items` in `2` columns when they have less of a `1000px` and all in `1` column when they are less than `500px` and for both cases, the `social icons` will be in the same `row` below the columns.

You may think that for the first part we will just need to change the `flex-direction` but that is not the case; let's see why

- Get to the `style.css` file
- At the bottom of the file; create a `media query` that handles the screen that is less than `1000px width`

    `@media all and (max-width:1000px) {}`

- Inside of the `media query`; select the `ul`

    ```css
    @media all and (max-width:1000px) {
        .flex-nav ul {}
    }
    ```

- On the new rule; add the `flex-direction` property with a value of `column`

    ```css
    @media all and (max-width:1000px) {
        .flex-nav ul {
            flex-direction: column;
        }
    }
    ```

- Save the file and refresh the page
- Resize your browser to be less than `1000px`
- You should see that all elements stack one on top of the other

We don't want this effect; we actually want 2 columns for the items and a single `row` for the `social icons`.

- Get to the `.flex-nav ul` inside of the `media query` and add the `flex-wrap` property with a value of `wrap` and remove the `flex-direction` property

    ```css
    @media all and (max-width:1000px) {
        .flex-nav ul {
            flex-wrap: wrap;
        }
    }
    ```

- Save the file and refresh the page
- Resize your browser to be less than `1000px`
- You should see that nothing happens

This is because to actually `wrap` elements the `container` need to have some `width`.

- Get to the `media query`
- Select the `li` elements

    ```css
    @media all and (max-width:1000px) {
        .flex-nav ul {
            flex-wrap: wrap;
        }

        .flex-nav li {}
    }
    ```

- Add the `flex` property with a value of `1` for the `flex-grow`/`flex-stretch` and `50%` as the `flex-basis`

    ```css
    @media all and (max-width:1000px) {
        .flex-nav ul {
            flex-wrap: wrap;
        }

        .flex-nav li {
            flex: 1 1 50%;
        }
    }
    ```

- Save the file and refresh the page
- Resize your browser to be less than `1000px`
- You should see that now we have `2` columns for the `nav` items(except for the `social ions`)
- Get to the `media query` and select the `social icons`

    ```css
    @media all and (max-width:1000px) {
        .flex-nav ul {
            flex-wrap: wrap;
        }

        .flex-nav li {
            flex: 1 1 50%;
        }

        .flex-nav .social {}
    }
    ```

- Give just `25%` size for the `social icons`

    ```css
    @media all and (max-width:1000px) {
        .flex-nav ul {
            flex-wrap: wrap;
        }

        .flex-nav li {
            flex: 1 1 50%;
        }

        .flex-nav .social {
            flex: 1 1 25%;
        }
    }
    ```

- Save the file and refresh the page
- Resize your browser to be less than `1000px`
- You should see that the `social icons` just occupy `25%` of the space each of them

Now we will work with the less than `500` viewport on which we will need to have just one column

- On the bottom of the `style.css` file; add a less than `500px media query`

    `@media all and (max-width:500px) {}`

- Select the `li` items on the newly created `media query`

    ```css
    @media all and (max-width:500px) {
        .flex-nav li {}
    }
    ```

- Now add the `flex-basis` property with a `100%` value

    ```css
    @media all and (max-width:500px) {
        .flex-nav li {
            flex-basis: 100%;
        }
    }
    ```

- Save the file and refresh the page
- Resize your browser to be less than `500px`
- You should see that all items are on one column(except the `social icons`)

As you see on the last `media query` we just use `flex-basis` because we set the other values before and we just want to overwrite this property.

## Mobile content reordering with flexbox

Now we are going to do an example using `order` and the most common thing that you can do is when you are making a responsive site someone can ask you to reorder the elements of the page for mobile so we can use the `flexbox order` to help us with this.

- Create a new directory for the new example
- On the newly created folder; create a new file called `index.html`
- In that newly created file; add the following content

    ```html
    <!DOCTYPE html>
    <html lang="en">
    <head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <title>FlexBox Nav</title>
    <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/font-awesome/4.3.0/css/font-awesome.min.css">
    <link rel="stylesheet" href="style.css">
    </head>
    <body>

    <div class="wrapper">

        <header class="top">
        <h1><a href="#">What The Flexbox?!</a></h1>
        </header>

        <nav class="flex-nav">
        <a href="#" class="toggleNav">☰ Menu</a>
        <ul>
            <li><a href="#">Item 01</a></li>
            <li><a href="#">Item 02</a></li>
            <li><a href="#">Item 03</a></li>
            <li><a href="#">Item 04</a></li>
            <li><a href="#">Item 05</a></li>
            <li><a href="#">Item 06</a></li>
            <li class="social">
            <a href="http://twitter.com/wesbos"><i class="fa fa-twitter"></i></a>
            </li>
            <li class="social">
            <a href="http://facebook.com/wesbos.developer"><i class="fa fa-facebook"></i></a>
            </li>
            <li class="social">
            <a href="http://github.com/wesbos"><i class="fa fa-github"></i></a>
            </li>
            <li class="social">
            <a href="http://instagram.com/wesbos"><i class="fa fa-instagram"></i></a>
            </li>
        </ul>
        </nav>

        <section class="hero">
        <img src="http://picsum.photos/1000/600">
        </section>

        <section class="details">
        <p>A simple video course to help you master FlexBox.</p>
        <p>Sign up today to grab all the videos and exercises!</p>
        </section>

        <section class="signup">
        <form action="" class="signup">
            <input type="text" placeholder="Your Name">
            <input type="email" placeholder="Email Address">
            <input type="submit" value="Sign me up!">
        </form>
        </section>

        <footer>
        <p>&copy; Test</p>
        </footer>


    </div>

    <script src="https://ajax.googleapis.com/ajax/libs/jquery/1.11.2/jquery.min.js"></script>
    <script>

        $(function() {
        $('.toggleNav').on('click',function() {
            $('.flex-nav ul').toggleClass('open');
        });
        });

    </script>
    </body>
    </html>
    ```

- Then on the same directory create a new file called `style.css`
- On the newly created file; add the following

    ```css
    html {
        box-sizing: border-box;
    }

    *, *:before, *:after {
        box-sizing: inherit;
    }

    body {
        font-family: sans-serif;
        margin: 0;
        background-image: linear-gradient(260deg, #2376ae 0%, #c16ecf 100%);
    }

    a {
        color:white;
        font-weight: 100;
        letter-spacing: 2px;
        text-decoration: none;
        background:rgba(0,0,0,0.2);
        padding:20px 5px;
        display: inline-block;
        width: 100%;
        text-align: center;
        transition:all 0.5s;
    }

    a:hover {
        background:rgba(0,0,0,0.3);
    }

    .toggleNav {
        display: none;
    }

    img {
        width:100%;
    }

    .wrapper {
        max-width: 1000px;
        margin: 0 auto;
    }

    input {
        padding:10px;
        border:0;
    }


    section, footer {
        text-align: center;
        background:rgba(0,0,0,0.2);
        padding:20px;
        margin:20px 0;
        color:white;
        font-weight: 100;
    }

    /* Flex Container */
    .flex-nav ul {
        border: 1px solid black;
        list-style: none;
        margin: 0;
        padding: 0;
        display: flex;
    }

    .flex-nav li {
        flex: 3;
    }

    .flex-nav .social {
        flex: 1;
    }

    @media all and (max-width:1000px) {

        .flex-nav ul {
            flex-wrap: wrap;
        }

        .flex-nav li {
            flex: 1 1 50%;
        }

        .flex-nav .social {
            flex: 1 1 25%;
        }
    }

    @media all and (max-width:500px) {

        .flex-nav li {
            flex-basis: 100%;
        }
    }
    ```

    On this file, we add the `nav` style that we added on the example of the preview and some more styling for the other elements so we can concentrate on the topic of the section.

- Save the files and open the `index.html` in the browser
- You will see a page with a `title`; the `nav`; an `image`; a `detail` section; an `email` section and a `footer`

For this example on the `500px media query` we will reorganize the section like this:

- At the top should be a `nav menu` but it will be hidden and a `toggle` button will be in charge of showing it(The `toggle` button is already set on the `HTML`)
- The second section will be the `title`
- The 3rd section will be the `detail` section
- Then the `email` section
- After that the `image` section
- And finally the `footer`

Let's begin with the process!!!

- On your editor; go to the `style.css` file
- Go to the `500 media query`
- Add select the `wrapper` property

    ```css
    .wrapper {
        display: flex;
    }
    ```

If you check on the `index.html` file you will see that all the elements are children of a `div` with a `wrapper` class and as you know we will use `order` for this example so every item should be a `flex item`.

- Save the file and refresh the page
- Resize your browser to have a size less than `500px`
- You should see that the page break

This is because as you may remember the default value of the `main axis` is from left to right because the `flex-direction` by default is `row`.

- Go to the `wrapper` class and add the `flex-direction` property with a `column` value

    ```css
    .wrapper {
        display: flex;
        flex-direction: column;
    }
    ```

- Save the file and refresh the page
- You should see that the page has all elements in a column
- Now let's work with the `nav`. Below the `wrapper` class on the `media query` select the `nav`

    ```css
    @media all and (max-width:500px) {

    .flex-nav li {...}

    .wrapper {...}

     .flex-nav {}
    ```

- Since the `nav` will be the first element; add the `order` property with a value of `1`

    ```css
    @media all and (max-width:500px) {

    .flex-nav li {...}

    .wrapper {...}

     .flex-nav {
         order: 1;
     }
    ```

- Save the file and refresh the page
- You should see that the `nav` get to the bottom of the page

This is because the default value of `order` is `0` so we will need to put a default `order` for the items

- Get to the `500 media query` and before the `flex-nav` class; select all elements that is a child of `wrapper`

    ```css
    @media all and (max-width:500px) {

    .flex-nav li {...}

    .wrapper {...}

    .wrapper > * {}

     .flex-nav {...}
    ```

- For all children of `nav` add the big number to the `order` property

    ```css
    @media all and (max-width:500px) {

    .flex-nav li {...}

    .wrapper {...}

    .wrapper > * {
        order: 9999;
    }

     .flex-nav {...}
    ```

- Save the file and refresh the page
- You should see the `nav` at the top of the page

Now as we mentioned we will have to hide the `nav` and show it when the user makes click on the `toggle` button. As you see on the `HTML` we have a `button` with a `toggleNav` class that is hidden for all sizes so we will need to show it first and hide the `nav`

- Get to the `500 media query` and select the `toggleNav` class and put a `display` property with a `block` value

    ```css
    @media all and (max-width:500px) {

    .flex-nav li {...}

    .wrapper {...}

    .wrapper > * {...}

     .flex-nav {...}

     .toggleNav {
         display: block;
     }
    ```

- Then hide the `nav` using the `display` property with a `none` value

    ```css
    @media all and (max-width:500px) {

    .flex-nav li {...}

    .wrapper {...}

    .wrapper > * {...}

     .flex-nav {...}

     .toggleNav {...}

    .flex-nav ul {
        display: none;
    }
    ```

- Save the file and refresh the page
- You should see the `toggle` button at the top

If you click the button it will not work but something is happening with the `nav` element

- Right-click on the page
- Click on inspect(Make sure that you can see the page and the inspector at the same time)
- Search for the `ul` inside of the `nav` element with a class of `flex-nav`
- Click the `toggle` button
- You should see that a class of `open` is added or removed from the `ul` element each time that you click the button

If you see at the end of the `HTML` file is a `jQuery` code that makes this possible. A class is just added and other functions to `toggle` are not used because those functions add a `display: block` to the element and that will mess with the `flex` style and put all elements in a single column but as you may remember the `social icons` are on the same `row`.

- Get to the `500 media query`
- Select the `URL` element of the `nav` when it has the `open` class

    ```css
    @media all and (max-width:500px) {

    .flex-nav li {...}

    .wrapper {...}

    .wrapper > * {...}

     .flex-nav {...}

     .toggleNav {...}

    .flex-nav ul {...}

    .flex-nav ul.open {}
    ```

- Add the `display` property with a `flex` value

    ```css
    @media all and (max-width:500px) {

    .flex-nav li {...}

    .wrapper {...}

    .wrapper > * {...}

     .flex-nav {...}

     .toggleNav {...}

    .flex-nav ul {...}

    .flex-nav ul.open {
        display: flex;
    }
    ```

- Save the file and refresh the page
- Click the `toggle` button
- You should see that the `nav` open/close each time that we click the button

Now we will need to add the `order` property to the `title` no matter that is in the correct position because we will change the `order` of the elements that are after that section and the default `order` value will push to the bottom the `title`.

- Get to the `500 media query`
- Select the `header` using the `top` class and add an `order` property with the value `2`

     ```css
    @media all and (max-width:500px) {

    .flex-nav li {...}

    .wrapper {...}

    .wrapper > * {...}

     .flex-nav {...}

     .toggleNav {...}

    .flex-nav ul {...}

    .flex-nav ul.open {...}

    .top {
        order: 2;
    }
    ```

- Then select the `details` and `signup` classes and add an `order` of `3` and `4` respectively

     ```css
    @media all and (max-width:500px) {

    .flex-nav li {...}

    .wrapper {...}

    .wrapper > * {...}

     .flex-nav {...}

     .toggleNav {...}

    .flex-nav ul {...}

    .flex-nav ul.open {...}

    .top {...}

    .details {
        order: 3;
    }

    .signup {
        order: 4;
    }
    ```

- Save the file and refresh the page
- You should see that all elements are in the `order` that we mentioned at the beginning of the section

## Nesting flexbox for vertical and horizontal centering

Now we will work with `nesting flexbox` when you have some more complex layouts. In this example, you will see a `slider` with one image and a bar below the image that has the `arrow` that will move the images back and forward(Which doesn't have the functionality to represent the example) and the name of different images that have different lengths(Will be links that can be clicked on any of at any part of it). We will want that the length of the item needs to be centered horizontally and vertically and for that, we will need to `nest flexbox`.

- Create a new folder for the new example
- On this newly created folder; create a file called` index.hml`
- Inside of the new file; add the following content

    ```html
    <!DOCTYPE html>
    <html lang="en">
    <head>
    <meta charset="UTF-8">
    <title>FlexBox Nav</title>
    <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/font-awesome/4.3.0/css/font-awesome.min.css">
    <link rel="stylesheet" href="style.css">
    </head>
    <body>
    <div class="wrapper">
        <div class="slider">
        <img src="slide.jpeg">
        </div>
        <nav class="slider-nav">
        <ul>
            <li class="arrow">
            <a href="#">←</a>
            </li>
            <li>
            <a href="#">Add a CLI to Node Apps with Vantage</a>
            </li>
            <li>
            <a href="#">NewSprint, Spectacle</a>
            </li>
            <li>
            <a href="#">Small Modules: Tales from a Serial Module Author</a>
            </li>
            <li>
            <a href="#">The End</a>
            </li>
            <li class="arrow">
            <a href="#">→</a>
            </li>
        </ul>
        </nav>
    </div>
    </body>
    </html>
    ```

- Now on the same directory; create a file called `style.css` with the following content

    ```css
    /* Some CSS Setup - nothing to do with flexbox */
    html {
        box-sizing: border-box;
    }

    *,
    *:before,
    *:after {
        box-sizing: inherit;
    }

    body {
        font-family: sans-serif;
        margin: 0;
        background-image: linear-gradient(260deg, #2376ae 0%, #c16ecf 100%);
    }

    .wrapper {
        max-width: 1000px;
        margin: 0 auto;
        padding: 50px;
    }

    img {
        max-width: 100%;
    }

    a {
        color: white;
        text-decoration: none;
        font-size: 15px;
        background: rgba(0, 0, 0, 0.2);
        padding: 20px 5px;
    }

    a:hover {
        background: rgba(0, 0, 0, 0.4);
    }

    .slider-nav ul {
        list-style: none;
        margin: 0;
        padding: 0;
    }
    ```

- Save both files and open `index.html` on the browser
- You will see an `image` and some items below the `image` in a column aligned to the left side(Looks broken)

As always we will need to set first the `flex container` and in this case the `ul`.

- Get to the `style.css` file
- Get tot the `.slider-nav ul` rule and add the `display` property with a `flex` value

    ```css
    .slider-nav ul {
        list-style: none;
        margin: 0;
        padding: 0;
        display: flex;
    }
    ```

- Save the file and refresh the page
- You will see that the items align themself in one `row`

As you can notice the items don't cover the complete size so you will have extra space at the right(use the image as a reference) so we will need to make that the items cover the complete space.

- At the bottom of the `style.css` file; select the `li` elements and add the `flex` property with a value of `1`

    ```css
    .slider-nav li {
        flex: 1;
    }
    ```

- Save the file and refresh the page
- You should see that the complete bar looks like not take up the complete space and there is some separation between items
- Get to the `li` rule and add a `border` to see what is happening

    ```css
    .slider-nav li {
        flex: 1;
        border: 1px solid red;
    }
    ```

- Save the file and refresh the page
- You should see the red border and that each item actually fills all the sizes available

The actual issue is the links because by default they are inline elements so we will need to change that and put that covert all `width` available.

- At the bottom of the `style.css` file; select the `a` tags and add the `display` property with a value of `block` also a `width` of a `100%`

    ```css
    .slider-nav a {
        display: block;
        width: 100%;
    }
    ```

- Save the file and refresh the page
- You should see that the anchors take all the `width` available

You also will see that not all the anchors take the complete `height` of the `li` because one of the anchors have a message with a bigger `length` than the others so the `li` will take the `height` of the bigger one.

Now we will want that the `arrows` take less space than the other items.

- On the `style.css` file; before `.slider-nav a` that is at the bottom; select the `arrows`

    `.slider-nav .arrow {}`

- Now add a `flex` property with a value of `1` in the `arrows`

    ```css
    .slider-nav .arrow {
        flex: 1;
    }
    ```

- Get to the `li` rule and change the `flex` property value to `2`

    ```css
    .slider-nav li {
        flex: 2;
        border: 1px solid red;
    }
    ```

- Save the file and refresh the page
- You should see that the items have more sizes than the `arrows`
- Get to the `li` rule and set the `text-align` property to be `center`

    ```css
    .slider-nav li {
        flex: 2;
        border: 1px solid red;
        text-align: center;
    }
    ```

- Save the file and refresh the page
- You should see that all elements are horizontally aligned in the center

Now we will need to align the items vertically so each of them is in the exact center of the container so we will try to use the `align-items` property to move it across the `cross axis`. Let's see if this helps us.

- Get to the `ul` container of the `flex items` and add the `align-items` property with a value of `center`

    ```css
    .slider-nav ul {
        list-style: none;
        margin: 0;
        padding: 0;
        display: flex;
        align-items: center
    }
    ```

- Save the file and refresh the page
- You should see that almost all items generate a space at the top(Between each item and the image) except the item that has more content

This is because the `align-items` property will move the items depending on the content and since we have one item bigger than the other will make generate that space. Remember that the default value of `align-items` is `stretch` and that is why before this update we have the anchors `stretch` to the bottom of the container but the anchors just have as much `height` as their content so to do what we want is to actually do both of then(`center` and `stretch`) at the same time but this is not possible from the `flex container` that we have at the moment, in other words, we will need that the `li stretch` all the way; the `anchor stretch` all the way and whatever is inside of the `anchor` will `vertically` align itself so we will need to use `nesting flexbox`.

When you are using `nesting flexbox` a `flex item` can be at the same time a `flex container` without any issues.

- Get to the `URL` rule and remove the `align-items` property
- At the `li` rule; add the `display` property with a `flex` value

    ```css
    .slider-nav li {
        flex: 2;
        border: 1px solid red;
        text-align: center;
        display: flex;
    }
    ```

- Save the file and refresh the page
- You should see that all anchors will fill the complete size of the `li` container
- Get to the `a` rule; and remove the `display` and `width` property
- In the same place add the `flex-basis` property with a `100%` value

    ```css
    .slider-nav a {
        flex-basis: 100%;
    }
    ```

- Save and refresh the page
- You should see that the items still fill all the `width` of the `li` container

At this moment we still have the `vertical-align` issue and as we tested before we can not use the `align-items` property because they need to be `stretch` so we will need to add a new element on our `HTML` that has the content of the `anchors` in this case we will need an element that doesn't affect our actual display on the page like a `span`.

- First; get to the `a` rule and make it a `flex container`

    ```css
    .slider-nav a {
        flex-basis: 100%;
        display: flex;
    }
    ```

- Save the file and refresh the page
- You should see that we just missing the alignment
- Get to the `index.html` file
- On each `anchor`; add a `span` for the content

    ```html
    <ul>
        <li class="arrow">
            <a href="#">
            <span>←</span>
            </a>
        </li>
        <li>
            <a href="#">
            <span>Add a CLI to Node Apps with Vantage</span>
            </a>
        </li>
        <li>
            <a href="#">
            <span>NewSprint, Spectacle</span>
            </a>
        </li>
        <li>
            <a href="#">
            <span>Small Modules: Tales from a Serial Module Author</span>
            </a>
        </li>
        <li>
            <a href="#">
            <span>The End</span>
            </a>
        </li>
        <li class="arrow">
            <a href="#"><span>→</span></a>
        </li>
    </ul>
    ```

- Save the file and refresh
- You should see that all the anchor content is aligned to the right

This is because by default the `span` is an `inline` element so we will need to change that and make that it takes `100%` of the `width` of the container.

- Get to the `style.css` file and at the bottom select the `span` element

    `.slider-nav span {}`

- Add the `display` property with a `block` value and a `width` of `100%`

    ```css
    .slider-nav span {
        display: block;
        width: 100%;
    }
    ```

- Save the file and refresh the page
- You should see that the content of the `anchors` are aligned to the center
- Get to the `style.css` file and on the `li`; remove the `border` property
- Then select the `anchor` on the `arrows` and add a `font-size` property of `30px`

    ```css
    .arrow a {
        font-size: 30px;
    }
    ```

- Save the file and refresh the page
- You should see that everything continues with the correct alignment regarding that we change the sizes of the `arrows`

## Flexbox pricing grid

In this section, we will build a columns grid and control the space inside of the columns so no matter the individual sizes of the content of the column their last element will be at the bottom without any space.

- Create a new folder to store the project
- Create a new file called `index.html` on this folder
- Add the following content to this newly created folder

    ```html
    <!DOCTYPE html>
    <html lang="en">
    <head>
        <meta charset="UTF-8">
        <title>FlexBox Nav</title>
        <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/font-awesome/4.3.0/css/font-awesome.min.css">
        <link rel="stylesheet" href="style.css">
    </head>
    <body>
        <div class="pricing-grid">
            <div class="plan plan1">
                <h2>Cat</h2>
                <p>Common, yet regarded by many as the worst house pet.</p>
                <ul class="features">
                    <li>Scratches everything</li>
                    <li>Easily lost for days</li>
                    <li>Kind of a bummer</li>
                </ul>
                <p class="price">free</p>
                <a href="#" class="cta">😾 Really?</a>
            </div>
            <div class="plan plan2">
                <h2>Dog</h2>
                <p>Loving, gentle and caring. Dogs are the best house pet to have and will increase happiness ten fold. </p>
                <ul class="features">
                    <li>Super Fun</li>
                    <li>Friends love them</li>
                    <li>Plays games</li>
                    <li>Not a cat</li>
                </ul>

                <p class="price">$90</p>

                <a href="#" class="cta">🐶 Best Deal →</a>
            </div>
            <div class="plan plan3">
                <h2>Fish</h2>
                <p>Cheap n' easy.</p>
                <ul class="features">
                    <li>Eats flakes</li>
                    <li>Cop out</li>
                    <li>Replaceable</li>
                </ul>
                <p class="price">$3</p>
                <a href="#" class="cta">🐠</a>
            </div>
        </div>
    </body>
    </html>
    ```

- On the same folder; create a file called `style.css`
- In this newly created file; add the following content

    ```css
    html {
        box-sizing: border-box;
    }

    *,
    *:before,
    *:after {
        box-sizing: inherit;
    }

    body {
        font-family: sans-serif;
        margin: 0;
        background-image: linear-gradient(260deg, #2376ae 0%, #c16ecf 100%);
    }

    a {
        color: white;
    }

    .plan ul {
        margin: 0;
        padding: 0;
        list-style: none;
    }

    .plan ul li {
        border-bottom: 1px solid rgba(0, 0, 0, 0.1);
        padding: 10px;
    }

    .plan ul li:last-child {
        border-bottom: 0;
    }

    .plan a {
        text-decoration: none;
        background: #FEFF00;
        padding: 10px;
        color: black;
        border-radius: 4px;
    }


    .plan h2 {
        text-transform: uppercase;
        color: white;
        letter-spacing: 2px;
        text-shadow: 3px 3px 0 rgba(0, 0, 0, 0.1);
    }

    .price {
        font-size: 50px;
        font-family: serif;
        margin: 10px 0;
    }

    .pricing-grid {
        max-width: 750px;
        margin: 0 auto;
    }
    ```

- Save both files and open the `index.html` on your browser
- You will see each `div` stuck one on top of the other with `pricing` information and without the column

Now let's get to work with `flex`

- Get to the `style.css` file
- In the `pricing-grid` class; create a `flex` container

    ```css
    .pricing-grid {
        max-width: 750px;
        margin: 0 auto;
        display: flex;
    }
    ```

- Save the file and refresh the page
- You should see that the 3 `div` are aligned on the same `row`(Since the second one have more content it will take more space for the text)

Now we will need to work with the `flex` items to distribute better the space

- At the bottom of the `style.css` file; add the `plan` class

    `.plan {}`

- On the `plan` class use the `flex` property with a value of `1`

    ```css
    .plan {
        flex: 1;
    }
    ```

- Save the file and refresh the page
- You should see that the items distribute their space equally
- Get to the `plan` class and add the following `background`

    ```css
    .plan {
        background: rgba(255, 255, 255, 0.2);
        flex: 1;
    }
    ```

- Also add some spaces around each item

    ```css
    .plan {
        background: rgba(255, 255, 255, 0.2);
        flex: 1;
        margin: 20px;
    }
    ```

- Then add some space between the content of each item and it border

    ```css
    .plan {
        background: rgba(255, 255, 255, 0.2);
        flex: 1;
        margin: 20px;
        padding: 20px;
    }
    ```

- Now add some border-radius at each corner and align the content to the center

    ```css
    .plan {
        background: rgba(255, 255, 255, 0.2);
        flex: 1;
        margin: 20px;
        padding: 20px;
        border-radius: 4px;
        text-align: center;
    }
    ```

- Save the file and refresh the page
- You should see that the items have some space between them and the content has space between the content and its border

Now the `height` of the columns is set by the one that has its biggest content so we will have some space at the bottom of the others but we will need that the buttons are always at the bottom of each column regarding its content.

As you remember the default behavior that will have each column will be `stretch`(align-items) at the time they were aligned but we actually want that behavior but at the same time we always want the button will be at the end so for this we will use `nested flex`

- Get to the `style.css` file
- On the `plan` class; add the `display` property with a value of `flex`

    ```css
    .plan {
        background: rgba(255, 255, 255, 0.2);
        flex: 1;
        margin: 20px;
        padding: 20px;
        border-radius: 4px;
        text-align: center;
        display: flex;
    }
    ```

- Save the file and refresh the page
- You should see that all content broke its alignment

This is because the `flex` property will try to make the content in one `row` so we will need to `wrap` all the content

- Get to the `plan` class and add the `flex-wrap` property with a value of `wrap`

    ```css
    .plan {
        background: rgba(255, 255, 255, 0.2);
        flex: 1;
        margin: 20px;
        padding: 20px;
        border-radius: 4px;
        text-align: center;
        display: flex;
        flex-wrap: wrap;
    }
    ```

- Save the file and refresh the page
- You should see that all content is in columns but still have some spacing and centering issues

To fix this we will need to select all the `flex items` and each of its content we will need to add the `flex grow stretch and basis` to take all the available space of the column.

- Below the `plan` class; select all the direct descendent

    `.plan > * {}`

- In this newly created rule; add the `flex` property with the following values

    ```css
    .plan > * {
        flex: 1 1 100%;
    }
    ```

- Save the file and refresh the page
- You should see that all content gets in the correct alignment
- Now at the bottom of the `style.css` file; select the buttons and `align` then to the `end`

    ```css
    .plan .cta {
        align-self: flex-end;
    }
    ```

- Finally; align the items of the `pricing-grid` to be at the center

    ```css
    .pricing-grid {
        max-width: 750px;
        margin: 0 auto;
        display: flex;
        align-items: center;
    }
    ```

- Save the file and refresh the page
- You should see that the columns are always center no matter the size of the biggest one

## Flexbox equal height columns and leftover elements

Now we will see how to do equal `height` columns and what we can do if we have some extra columns at the end.

- Create a new folder to store the example
- On the new folder; create a new file called `index.html`
- In this newly created file; add the following content

    ```html
    <!DOCTYPE html>
    <html lang="en">
        <head>
            <meta charset="UTF-8">
            <title>Example</title>
            <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/font-awesome/4.3.0/css/font-awesome.min.css">
            <link rel="stylesheet" href="style.css">
        </head>
        <body>
            <div class="elements">
                <div class="item">You can tell the world you never was my girl</div>
                <div class="item">You can burn my clothes when I'm gone</div>
                <div class="item large">Or you can tell your friends just what a fool I've been</div>
                <div class="item">And </div>
                <div class="item">You </div>
                <div class="item small">You </div>
                <div class="item">Or you can tell my lips to tell my fingertips</div>
                <div class="item small">They won't be reaching out for you no more</div>
                <div class="item large">But don't tell my heart my achy breaky heart</div>
                <div class="item">I just don't think he'd understand</div>
                <div class="item small">And if you tell my heart</div>
                <div class="item large">my achy breaky heart</div>
                <div class="item">He might blow up and kill this man</div>
                <div class="item">[guitar]</div>
                <div class="item">You can tell your ma I moved to Arkansas</div>
                <div class="item large">You can tell your dog to bite my leg</div>
                <div class="item">Or tell your brother Cliff whose fist can can tell my lip</div>
                <div class="item small">He never really liked me anyway</div>
                <div class="item">Or tell your Aunt Louise tell anything you please</div>
                <div class="item">Myself already knows I'm not okay</div>
                <div class="item large">Or you can tell my eyes to watch out for my mind</div>
                <div class="item">It might be walking out on me today</div>
                <div class="item">Don't tell my heart my achy breaky heart...</div>
                <div class="item">[guitar]</div>
                <div class="item">Don't tell my heart my achy breaky heart...</div>
                <div class="item">Don't tell my heart my achy breaky heart...</div>
            </div>
        </body>
    </html>
    ```

- Then create a new file called; `style.css` on the same directory
- Add the following content

    ```css
    html {
        box-sizing: border-box;
    }

    *,
    *:before,
    *:after {
        box-sizing: inherit;
    }

    body {
        font-family: sans-serif;
        margin: 0;
        background-image: linear-gradient(260deg, #2376ae 0%, #c16ecf 100%);
    }

    a {
        color: white;
    }

    .item.large {
        font-size: 40px;
    }

    .item.small {
        font-size: 20px;
    }

    .item {
        background: rgba(255, 255, 255, 0.2);
        margin: 10px;
        padding: 20px;
        font-size: 30px;
    }
    ```

- Save both files and open the `index.html` file on the browser
- You should see different `rows` with the text of different sizes

Now we will make columns and will be the `equal height` of the `highest` one

- Get to the `style.css` file
- Select the `elements` container

    `.elements {}`

- Add the `display` property with a `flex` value

    ```css
    .elements {
        display: flex;
    }
    ```

- Save the file and refresh the page
- You should see that every item is in a column and take all the `width` available on the page

But we will need that we have multiple `rows` and not just to put everything in a single one that overflows the `width` of the page so we will need to `warp` the `flex items`

- Go to the `style.css` file
- On the `elements` class; add the `flex-wrap` property with a `wrap` value

    ```css
    .elements {
        display: flex;
        flex-wrap: wrap;
    }
    ```

- Save the file and refresh the page
- You should see that the elements distribute it on multiple `rows` and depending on the `width` of an item will put one or more in a single `row`

If you change the size of the screen with reorganize the number of items of each `row` but we actually need that we always have at least 3 items per `row` so we will need to add a `width` to each item.

- Get to the `style.css` file
- Select the `items`

    `.items {}`

- Use the `flex` property on each item and put a value of `1` for the `flex-grow` and `flex-stretch` then `33.33%` for the `flex-basis`

    ```css
    .items {
        flex: 1 1 33.33%;
    }
    ```

- Save the file and refresh the page
- You should see that the elements are 2 on each `row`

This is because on the styles that we add at the beginning `item` has a `margin` of `10px` so we over budget the `width` of the screen so automatically it will pass the third element to the next `row` and resize the 2 remaining columns so it will take all the available space. To fix this we will need to take the `margin` into consideration on the `flex-basis`.

- Go to the `items` class
- Use `calc` on the `flex` property to take the `20px` of `margin` into consideration

    ```css
    .items {
        flex: 1 1 calc(33.33% - 20px);
    }
    ```

- Save the file and refresh the page
- You should see that you have 3 elements per `row`

So by default, you see that each `row` is as `height` as the one that has the biggest `height`.

- Scroll to the bottom
- You will see just 2 items on the last `row`

This is because the number of items that we have is not divisible by 3 so it remains just 2 items at the end so `flex` adjust the space of both items with the available space. We can change this using `flexbox` if we need.

- Get to the `elements` class and add a `justify-content` property with a `space-between` value

    ```css
    .elements {
        display: flex;
        flex-wrap: wrap;
        justify-content: space-between
    }
    ```

- Save the file and refresh the page
- You should see that nothing happened with the last 2 items

This is because we told that `flex-grow` to split equally the extra amount of space so we will need to change this

- Get to the `items` class and add a value of `0` for the `flex-grow`

    ```css
    .items {
        flex: 0 1 calc(33.33% - 20px);
    }
    ```

- Save the file and refresh the page
- You should see that the last 2 items are on both the start and end side of the `row` with a lot of space in the middle

This is because we actually said that do nothing with the extra space when we change the `flex-grow` and have the sizes that we told so the other extra space will be in the middle.

- Get to the `elements` class
- Change the `justify-content` value to `space-around`
- Save the file and refresh the page
- You should see that now there are spaces before and after both items

So you can align what you want or simply leave that `stretch` the items as they need.

## Flex single-line form

Now we will work with a `form` using `flexbox` so we will have a single line `form` that we can fit together using `flex`.

- Create a new folder for the example
- On the new folder; create a new file called `index.html`
- In the new file; add the following content

    ```html
    <!DOCTYPE html>
    <html lang="en">
        <head>
            <meta charset="UTF-8">
            <title>FlexBox form</title>
            <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/font-awesome/4.3.0/css/font-awesome.min.css">
            <link rel="stylesheet" href="style.css">
        </head>
        <body>
            <div class="cover">
                <form  class="flex-form">
                <input type="search" placeholder="Where do you want to go?">
                <label for="from">From</label>
                <input type="date" name="from">
                <label for="from">To</label>
                <input type="date" name="to">
                <select name="" id="">
                    <option value="1">1 Guest</option>
                    <option value="2">2 Guest</option>
                    <option value="3">3 Guest</option>
                    <option value="4">4 Guest</option>
                    <option value="5">5 Guest</option>
                </select>
                <input type="submit" value="Search">
                </form>
            </div>
            <video  class="dog" src="cover/name_of_your_cover.webm" autoplay muted loop></video>
        </body>
    </html>
    ```

- On your browser go to https://coverr.co/
- Download a video
- Get to the example folder
- Create a new folder called `cover`
- Add the video that you just downloaded to the `cover` folder
- Go to the `index.html`
- On the `video` tag; add the path of the video that is on the `cover` folder in the `src` property
- Now on the same example folder; create a new file called `style.css`
- Add the following content to the `style.css` file

    ```css
    html {
        box-sizing: border-box;
    }

    *,
    *:before,
    *:after {
        box-sizing: inherit;
    }

    body {
        font-family: sans-serif;
        margin: 0;
        overflow: hidden;
        background-image: linear-gradient(260deg, #2376ae 0%, #c16ecf 100%);
    }

    a {
        color: white;
    }

    .cover {
        height: 100vh;
        width: 100%;
    }

    /*Video*/

    .dog {
        height: 100%;
        -webkit-filter: blur(5px);
        filter: blur(5px);
        position: absolute;
        top: 0;
        z-index: -1;
    }

    /*Hack to get them to align properly */
    .flex-form>*:not([type="date"]) {
        border-top: 1px solid white;
        border-bottom: 1px solid white;
    }

    .flex-form input[type="submit"] {
        background: #FF5A5F;
        border-top: 1px solid #FF5A5F;
        border-bottom: 1px solid #FF5A5F;
        color: white;
    }

    .flex-form {
        z-index: 10;
        position: relative;
    }

    .flex-form>* {
        border: 0;
        padding: 10px;
        background: white;
        line-height: 50px;
        font-size: 20px;
        border-radius: 0;
        outline: 0;
        border-right: 1px solid rgba(0, 0, 0, 0.2);
        -webkit-appearance: none;
    }

    .flex-form>*:last-child {
        border-right: 0;
    }
    ```

- Save both files and open the `index.html` on the browser
- You should have a single line `form` at the top of the page that has the video as background

You should see that not all `inputs` are the same size and have some space between them; this space is called `gosh space` that is caused because the `inputs` are `inline` elements by default and add this space. So the first thing that we are going to do is to center the `form` both vertically and horizontally.

- Get to the bottom of the `style.css` file
- Select the `inputs` container

    `.cover {}`

- Add a `display` property with a `flex` value

    ```css
    .cover {
        display: flex;
    }
    ```

- Save the file and refresh the page
- You don't see any change because this is just one item

Now lets `center` the `form` horizontally

- Get to the `cover` class; and add the `justify-content` property with a `center` value

    ```css
    .cover {
        display: flex;
        justify-content: center;
    }
    ```

- Save the file and refresh the page
- You should see that the `form` is centered horizontally

Now let's try to `center` the `form` vertically

- Get to the `cover` class and add the `align-items` property with a `center` value

    ```css
    .cover {
        display: flex;
        justify-content: center;
        align-items: center;
    }
    ```

- Save the file and refresh the page
- You should see that the `form` is centered vertically on the page

Now we will need to work with the items of the `form` so we will need to do a `flex container` first because `cover` is the container of the `form` tag and the `form` tag will be the container of each item

- Select the `form` tag

    `.flex-form {}`

- Add the `display` property with a value of `flex`

    ```css
    .flex-form {
        display: flex;
    }
    ```

- Save the file and refresh the page
- You should see that each item gets the same `height`

This is because it takes every item and `stretches` it(by default) that making it the same size. Now we will add `border` on the `form`(just for styling)

- Get to the `flex-form` class and add the following

    ```css
    .flex-form {
        display: flex;
        border: 20px solid rgba(0, 0, 0, 0.3);
        border-radius: 5px;
    }
    ```

- Save the file and refresh the page
- You should see a new `border` for the `form`

Finally, we will add some more space to the `search` input so we can see the `placeholder` text.

- Get to the bottom of the `style.css` file
- Select the `search` input

    `input[type="search"] {}`

- Add the `flex-basis` property with a `500px` value

    ```css
    input[type="search"] {
        flex-basis: 500px;
    }
    ```

- Save the file and refresh the page
- You should see that the `search` input has more space

As you see with just a couple of `flex` properties we achieved our objective.

