# CSS: How to Center Elements with CSS

**Objective:** In this article, you will know dependency injection concept, to center a div horizontally and vertically in CSS.

**Pre-requisite** Prior to completing this article, you should have already installed all pre-requisite tooling including: Visual Studio Code, Nodepad etc.

1.  **Text-Align Approach**

The most common way of centering is to align the text to the center. In other words, set the parent element to **text-align: center** and the children element to **display: inline-block**.

Pretty self-explanatory, you might say.

2. **The (Classic) Absolute Approach**

A classic way of centering elements is to set the parent element to absolute (or fixed) and set the top and left properties by 50%.

To move the element to the other direction, you translate the x-axis and y-axis by -50% with the transform property.

Here’s what the final code should look like:

```node
.wrapper {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translateX(-50%, -50%);
}
```
This perplexing hack was the gold standard before. But in 2009, CSS introduced Flexbox.

3. **Flexbox Approach**

In this approach, we set the parent element into a flexible column or row, then align and justify the children to the center using align-items and justify-content.

One thing to note: align-items is for vertical centering and justify-content is for horizontal centering.

```node
.wrapper {
    display: flex;
    align-items: center;
    justify-content: center;
}
```

But what if we can center the div block with less code? That’s where the grid comes in, and it’s shorter than you think.

4. **The (Two-Lined) Grid Approach**

Here’s a shorter way to center elements. Define the parent element as a grid and tell it to place the items inside to center.

```node
.wrapper {
     display: grid;
     place-items: center;
}
```
See? That’s even shorter.


**Source Code & Reference**

- [How to Center text Horizontally and Vertically in CSS](https://medium.com/@codegridweb/how-to-center-text-horizontally-and-vertically-in-css-67e24ceb573f),
- [Top 3 ways to center a DIV with CSS](https://www.youtube.com/watch?v=njdJeu95p6s),
- [Center CSS With Style](https://betterprogramming.pub/how-to-center-things-with-style-in-css-dc87b7542689)



