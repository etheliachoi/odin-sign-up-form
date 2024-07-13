# Sign-up Form
## Description
This is the first project for the Intermediate HTML and CSS course of The Odin Project. We are given a design file of a sign-up form and the task is to recreate it using HTML forms.

## Process
My first thought is to split the page in half, one side for the image and the other for the form elements. My approach is to use grids to layout the page structure. Once the main elements like the polar bear image are fitted perfectly within its container, styling the form is not too difficult.

## Challenges
**(1)** Initially, I used 5 rows for the left hand side on the page, `grid-template-rows: 1fr 1fr 2fr 1fr 1fr;` such that the first and last row can account for the empty space at the top and bottom of the page. However, when I shrunk the viewport horizontally by a little, the right side of the page becomes much longer than left side.

**Solution**: I removed the two empty rows from the `grid-template-rows` and used `align-content: end` to move the intro paragraph closer to the sign-up form and create the empty space effect.

----

**(2)** When I used `grid-template-columns: repeat(2, 1fr);` for the overall page layout and shrunk the viewport extremely small, the layout was no longer half-half horizontally.  

**Solution**: I changed to `grid-template-columns: 50% 50%;` and the issue is completely solved.

----

**(3)** After adding the grey bar that now containes the Odin logo and text, I found that the bar reamins in the position as I scroll down the page or when the viewport is small. 

**Solution**: Changed from `position: fixed;` to `position: absolute;` for the bar.

----
**(4)** Upon finishing 100% of the layout and 98% of the styling, one of my last tasks was to validate the password with attributes of the `<input>` element. This was when I realized the submit button was placed outside of the `<form>` element, so I was unable to submit or validate information typed into the form. 

**Solution**: Instead of re-structuring the HTML and re-doing the CSS, I linked the `<button>` to the `<form>` using the id attribute and all went well.

----

**(5)** I made the password input `required`, so when I want to check whether the user input is invalid, i.e. does not match the pattern, I used the pseudo-class `:invalid` and made the border red if it holds. However, this caused the field to be red even when the user has not typed in anything, since an input is invalid when it is empty.

**Solution**: I used `:user-invalid` instead, which checks the requirements after the user has interacted with the element.

----

**(6)** After solving (1), I realized the problem with the forms side being longer at a certain viewport still exists, except that the viewport size only breaks when it is shrunk extremely small.

**Solution**: My hypothesis is that the image cannot be shrunk further without breaking the dimensions and becoming distorted. However, the issue remains unresolved.

## What I learned
I finished the final project of the course before tackling this one, which made it much easier with the knowledge and experience with grids. I found building forms rather easy to pick up but styling them could be tricky. For example, it is challenging making the input field a reasonable size and have them shrink accordingly with the label. 

This project is the first time I used `position` properties. For example, placing the polar bear image such that the bear remains in the middle, adding the grey bar on top of the image without it becoming a grid item, and adding more items on top of the grey bar. 

Overall, I learned a lot through carefully thinking of the parent-child relationship and how to place things such that they become grid items or potential flexboxes which I can control the placement of. I also gained a lot of experience incoporating and experimenting with different units such that the page is flexible and does not break at different viewport sizes. For example, taking advantage of the parent container to define height and widths with %.