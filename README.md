# Restaurant Website
The objective of this project was to develop a simple, interactive restaurant website using only JavaScript to dynamically generate all the webpage content. This approach avoids hardcoding HTML in the body, and instead uses the Document Object Model (DOM) to create and inject all elements through script.

To start, I defined a helper function named createEl(). This function simplifies the creation of elements by allowing me to set attributes, inner text or HTML, and append children — all in one call. This reduced code redundancy and made it easier to manage nested structures like forms and sections.

Using this function, I dynamically created all the core parts of a website:

A header section with the restaurant’s name and tagline.

A navigation bar with links to the Menu and Contact sections.

A menu section, where each dish (name and description) was defined in an array and rendered dynamically using a loop.

A contact section containing a form with input fields for name, email, and message.

For interactivity, I added a JavaScript event listener to the contact form. When the form is submitted, it checks that all fields are filled and displays a confirmation message using DOM manipulation.

I also applied CSS styles in the <style> tag within the <head>, ensuring the layout is clean, responsive-friendly, and visually appealing. Styles were kept simple, using familiar color schemes and spacing for readability.

Finally, I appended all sections (header, nav, content, and footer) directly to the body using JavaScript.

This project enhanced my understanding of DOM manipulation, dynamic UI creation, and event-driven programming in JavaScript. It also reinforced clean code practices and structuring web applications without relying on static HTML.
