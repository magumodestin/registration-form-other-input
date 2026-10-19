# Registration Form with Conditional "Other" Gender Input

A clean, responsive registration form built with HTML, CSS, JavaScript and PHP. When a user selects **Other** from the gender dropdown, an extra text field appears so they can specify their gender. For any other choice, the field stays hidden.

## Features

- Styled card layout with a gradient background
- Gender dropdown (`Male`, `Female`, `Other`)
- "Please specify other gender" input that appears only when `Other` is selected
- Smooth slide-in animation and automatic focus on the new input
- The extra field becomes required only when visible, and is cleared when hidden
- Fully responsive (works on phones, tablets and desktops)
- PHP handler that saves the specified text instead of the word "other"

## Technologies Used

- HTML5
- CSS3 (Flexbox, transitions, keyframe animation)
- JavaScript (vanilla)
- PHP
- MySQL (optional, for storing submissions)

## Project Structure

```
registration-form/
├── index.html      # Form, styles and script (single file)
├── process.php     # Handles the submitted form data
└── README.md
```

> Tip: for larger projects, split `index.html` into `index.html`, `style.css` and `script.js`.

## How It Works

1. The user picks an option from the gender `<select>`.
2. JavaScript listens for the `change` event on the dropdown.
3. If the value is `other`, the hidden text box is shown and set to `required`.
4. If any other option is chosen, the box is hidden, no longer required, and its value is cleared.
5. On submit, `process.php` checks the value. If it is `other`, it uses the text the user typed.

```php
$gender = $_POST['gender'] ?? '';

if ($gender === 'other') {
    $gender = trim($_POST['otherGender'] ?? '');
}
```

## Getting Started

### Run locally with XAMPP

1. Install and start **XAMPP** (Apache, and MySQL if you want to save data).
2. Copy the project folder into `C:\xampp\htdocs\`.
3. Open your browser and go to:
   ```
   http://localhost/registration-form/index.html
   ```

### Run without PHP

Open `index.html` directly in your browser to try the form and the show/hide behaviour. Submitting will only work when served through a PHP server.

## Customization

- **Theme color:** replace `#4f46e5` in the CSS with any color you like.
- **Background:** edit the `linear-gradient(...)` on `body`.
- **More options:** add extra `<option>` tags to the dropdown (for example `Prefer not to say`).
- **Extra fields:** copy a `.form-group` block to add email, phone number and so on.

## Possible Improvements

- Save submissions to a MySQL database
- Add server-side validation and sanitization
- Add a dark/light mode toggle
- Show success and error messages after submitting

## License

This project is open source and free to use for learning and practice.
