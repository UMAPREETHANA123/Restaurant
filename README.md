<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Delicious Bites - JavaScript Website</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      margin: 0; padding: 0;
      background-color: #fffaf0;
    }
    header {
      background-color: #e67e22;
      color: white;
      padding: 20px;
      text-align: center;
    }
    nav {
      background-color: #f39c12;
      text-align: center;
      padding: 10px;
    }
    nav a {
      color: white;
      margin: 0 15px;
      text-decoration: none;
      font-weight: bold;
      cursor: pointer;
    }
    section {
      padding: 20px;
    }
    .menu-item {
      border-bottom: 1px solid #ccc;
      padding: 10px 0;
    }
    form {
      background-color: #f4f4f4;
      padding: 20px;
      border-radius: 5px;
      max-width: 400px;
      margin: auto;
    }
    form input, form textarea {
      width: 100%;
      padding: 10px;
      margin-top: 10px;
    }
    form button {
      background-color: #e67e22;
      color: white;
      padding: 10px;
      border: none;
      margin-top: 10px;
      cursor: pointer;
    }
    footer {
      text-align: center;
      padding: 15px;
      background-color: #eee;
      margin-top: 40px;
    }
  </style>
</head>
<body>
  <script>
    // Helper to create elements
    function createEl(tag, options = {}, ...children) {
      const el = document.createElement(tag);
      for (let key in options) {
        if (key === 'class') el.className = options[key];
        else if (key === 'html') el.innerHTML = options[key];
        else el.setAttribute(key, options[key]);
      }
      children.forEach(child => {
        if (typeof child === 'string') el.appendChild(document.createTextNode(child));
        else if (child) el.appendChild(child);
      });
      return el;
    }

    // Header
    const header = createEl('header', {}, 
      createEl('h1', {}, 'Delicious Bites'),
      createEl('p', {}, 'Where taste meets tradition')
    );

    // Navigation
    const nav = createEl('nav', {}, 
      createEl('a', {href: '#menu'}, 'Menu'),
      createEl('a', {href: '#contact'}, 'Contact')
    );

    // Menu Section
    const menuSection = createEl('section', {id: 'menu'}, 
      createEl('h2', {}, 'Our Menu')
    );

    const menuItems = [
      {name: 'Margherita Pizza', desc: 'Classic cheese pizza with fresh basil - ₹250'},
      {name: 'Pasta Alfredo', desc: 'Creamy white sauce pasta with mushrooms - ₹300'},
      {name: 'Paneer Tikka', desc: 'Spicy grilled paneer with mint chutney - ₹220'}
    ];

    menuItems.forEach(item => {
      const div = createEl('div', {class: 'menu-item'}, 
        createEl('h3', {}, item.name),
        createEl('p', {}, item.desc)
      );
      menuSection.appendChild(div);
    });

    // Contact Section
    const contactSection = createEl('section', {id: 'contact'}, 
      createEl('h2', {}, 'Contact Us')
    );

    const form = createEl('form', {id: 'contactForm'}, 
      createEl('input', {type: 'text', id: 'name', placeholder: 'Your Name', required: true}),
      createEl('input', {type: 'email', id: 'email', placeholder: 'Your Email', required: true}),
      createEl('textarea', {id: 'message', rows: 4, placeholder: 'Your Message', required: true}),
      createEl('button', {type: 'submit'}, 'Send')
    );

    const confirmMsg = createEl('p', {id: 'confirmation', style: 'text-align:center; color:green; margin-top:15px;'});

    contactSection.appendChild(form);
    contactSection.appendChild(confirmMsg);

    // Footer
    const footer = createEl('footer', {}, 
      '© 2025 Delicious Bites | All rights reserved.'
    );

    // Append all to body
    document.body.appendChild(header);
    document.body.appendChild(nav);
    document.body.appendChild(menuSection);
    document.body.appendChild(contactSection);
    document.body.appendChild(footer);

    // Form submission logic
    form.addEventListener('submit', function(event) {
      event.preventDefault();
      const name = document.getElementById('name').value;
      const email = document.getElementById('email').value;
      const message = document.getElementById('message').value;

      if (name && email && message) {
        confirmMsg.textContent = `Thanks for contacting us, ${name}!`;
        form.reset();
      } else {
        confirmMsg.textContent = 'Please fill in all fields.';
      }
    });
  </script>
</body>
</html>
