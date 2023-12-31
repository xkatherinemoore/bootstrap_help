<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Bootstrap Practice</title>

    <!--STYLESHEETS-->
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-9ndCyUaIbzAi2FUVXJi0CjmCapSmO7SnpJef0486qhLnuZ2cdeRhO02iuK6FUUVM" crossorigin="anonymous">
    <link rel="stylesheet" href="css/main.css">
    <link rel="stylesheet" href="css/bootstrap-breakpoint.css">

</head>
<body>
    <div class="container-md">
        <div class="row">
            <div class="col">
                <div class="box"></div>
            </div>
            <div class="col">
                <div class="box"></div>
            </div>
            <div class="col">
                <div class="box"></div>
            </div>
        </div>
        Lorem ipsum dolor sit amet, consectetur adipiscing elit. Vestibulum tellus diam, elementum vitae orci et, accumsan sodales nulla. Suspendisse non congue odio, vel vulputate enim. Morbi eget dolor aliquam, venenatis leo sed, ultrices felis. Proin condimentum aliquam ante, sed rutrum enim egestas sit amet. In placerat imperdiet posuere. Praesent et dui lectus. Nunc interdum mattis dapibus. Proin vestibulum quam a tristique tempor. Quisque in sodales sapien. Etiam placerat arcu at laoreet volutpat. In nec orci dictum, pulvinar enim at, accumsan diam.

        Breakpoints
        Below the specified breakpoint (sm/md/lg/xl/xxl), the container will fill the screen (100%). At the breakpoint and above, the container will have padding
        container-fluid means the screen will always be 100%
        Almost all bootstrap classes will have a breakpoint version which specifies for that screen size and above
            default_class-breakpoint-size

        Spacing values are usually between 0-5
        g: gap (both x and y)
            gx: horizontal gap
            gy:

        Rows and Columns
        Rows use flexbox which means everything in a row (col) will adjust to fill the row
        - By default, columns will all be equal in size, adjusting to fill the container
        Bootstrap uses a 12-column grid, so columns should add up to 12
        - col-md-4 means on a medium screen or larger, it will be 4 columns wide. On xs/sm screens, the width will default to 100% unless specified otherwise (like col-8)
        
        offset-# class allows you to add empty space between columns (offset the column # of columns)
        row-cols-2 class will specify 2 columns per row; additional cols will wrap 
        row-cols-lg-4
        Nesting rows: a column can contain another row which can contain another column

        Tables
        use class="table" to the table element to add standard formatting
        table-color: can be added to any table element; will make the background of that element the color specified
        table-striped: alternate colors for each row
        table-striped-column: alternate colors for each column
        table-hover: when the mouse hovers over a row in the table, it is highlighted a different color
        table-active: can be added to tr to highlight the row as if it was being hovered over
        table-bordered: adds borders to the table (around each cell)
        table-borderless: removes all borders from table
        table-sm: removes some of the padding between rows to consolidate table
        table-group-divider: can only be used in thead, tbody, or tfoot sections; adds a distinct top-border

        Creating a div container with class="table-responsive" that contains the table will create a table that can scroll from side-to-side 
        - Can include a breakpoint so that the table is only scrollable below a certain screen size
        - Table will overflow by default if too wide for the screen (based on number of table columns)

        Forms
        form-label: for label elements:
        form-control: for text (and similar) input elements;
            - sm and lg will change the input size
        form-select: for select elements
        form-check: Use a separate div that wraps the input and label elements
            form-check-input: include in input element
            form-check-label: include in label element
            form-switch: creates a toggle switch for checkbox; include in form-check div
            form-check-inline: changes display to inline instead of block include in form-check div

        <form>
            <label for="text" class="form-label">Amount</label>
            <div class="input-group">
                <div class="input-group-text">$</div>
                <input type="number" id="text" class="form-control">
                <div class="input-group-text">.00</div>
            </div>
            <button class="btn">Submit</button>
        </form>
            
            Input Group
            Allows for different inputs to be grouped together
            - Think first name and last name entered on the same line as Name but with two separate inputs
            - .input-group-text should be contained in a div and adds text to the input field that cannot be edited
        
            Floating labels
            Puts the label into the input field and when the input field is clicked, the label floats up
            Note that the label element must come after the input element and the input must have a placeholder value
            <div class="form-floating">
                <input type="email" id="email" class="form-control" placeholder="Email">
                <label for="email" class="form-label">Email</label>
            </div>

            Form Validation
            The script below will add the class .was-validated to the form element
            .was-validated class is a Bootstrap class that will automatically add visual validation cues to the inputs within the form
            Need to include novalidate attribute in the form element to work properly

            <form novalidate>
                <div class="floating label">
                    <input type="tel" id="phone" placeholder="Phone Number" class="form-control">
                    <label for="phone" class="form-label">Phone Number</label>
                    <div class="invalid-feedback">Invalid Phone Number</div>
                    <div class="valid-feedback">Valid Phone Number</div>
                </div>
                <button type="submit" class="btn">Submit</button>
            </form>

            <script>
                const form = document.querySelector("form");

                form.addEventListener('submit', e => {
                    if (!form.checkValidity()) {
                        e.preventDefault();
                    }

                    form.classList.add('was-validated');
                });
            </script>
        
        Colors
        primary:
        secondary
        success
        danger
        warning
        info
        light
        dark

        Buttons
        .btn is default class for buttons
        Can be used on both button tags and anchor tags
        .btn-group links buttons together

        Alerts
        .alert class will appear at the top of the screen
        include role="alert" for accessiblity
        .alert-dismissible makes it so that the user can close the alert
            Requires adding a close button with data-bs-dismiss="alert" and .btn-close class

        data-bs-* attributes are used to access some BootStrap JavaScript
            data-bs-toggle: will toggle something in and out 
        data-bs-target is used to point to whatever is being changed (usually an id)

        Collapse
        .collapse and .show are used to give the initial state
        data-bs-target="collapse"
        - Need aria-expanded and aria-controls attributes for accessibility
        Can be used for multiple elements

        Navbar
        1. Include within the nav element with .navbar and (usually) .navbar-expand-breakpoint
        2. Include a div container that is the same as your main content so everything lines up
        3. .navbar-brand can be added to the brand link/photo
        4. Navigation links are usually included in a ul list with .navbar-nav 
        5. li elements need to be .nav-item 
        6. a elements need to be .nav-link 

        To create a collapsed navbar, include whatever needs to be collapsed in a div element with .collapse .navbar-collapse 
            button .navbar-toggler-icon will give the standard three-line toggler 


        ARIA
        Used for screen readers to explain what elements do
        aria-controls: specifies what element a button will act on 
        aria-label: A label explaining the element

        Color Utilities
        Use the following as classes to add styling components
        bg-*: background color
        bg-opacity-*: changes the opacity of the background
        text-*: font color
        text-opacity-*: changes the opacity of the font
        text-bg-*: background color specified with a high contrast standard text color
        link-*: changes the color of the link text while still keeping functionality like hover 
        opacity-*: can be used to change the opacity of an entire object 

        Stack Utilities 
        Used to easily add flexbox utiltiies to items
        hstack: stack items horizontally
        vstack: stack items vertically
        gap-*: used to add margins between items


        Border Utilities 
        .border will add a border to an object 
        Can use colors, sides, opacity 
        rounded-*: Rounds out the border with different options 

        Display Utilities 
        d-* to set the display property
        d-none will hide an object 
        Can be used with breakpoints to hide an object above/below a certain breakpoint 

        Spacing 
        m-*: Used for margins 
        p-*: Used for padding 
        Can use values between 0-5 and auto 
        Can use breakpoints 
        top (t), right (e), bottom (b), and left (s) 
        x and y for horizontal or vertical 

        Flexbox Layouts
        justify-content-* is used for aligning objects within a container 
        align-items-* is used to manage alignment of grouped objects with each other

    </div>
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/js/bootstrap.bundle.min.js" integrity="sha384-geWF76RCwLtnZ8qwWowPQNguL3RmwHVBC9FhGdlKrxdiJJigb/j/68SIy3Te4Bkz" crossorigin="anonymous"></script>
</body>
</html>

