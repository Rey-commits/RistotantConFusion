#  **Ristorant ConFusion**


### **Setting up the Project Folder**

* Open a cmd window/terminal and move to the conFusion folder.
At the prompt type:

`npm instal`

* This will install the lite-server node module to your project.
* Next, initialize a Git repository in the project folder, and then set up a .gitignore file with the contents as shown below:

`node_modules`

### **Downloading Bootstrap**

* You will use npm to fetch the Bootstrap files for use within your project. At the prompt, type the following to fetch Bootstrap files to your project folder:

`npm install bootstrap@4.0.0-alpha.6 --save`

* This will fetch the Bootstrap files and store is in your node_modules folder in a bootstrap folder. The bootstrap->dist folder contains the precompiled Bootstrap CSS and JS files for use within your project.
* Open your project folder in your editor, and then open the index.html file in the conFusion folder. This is your starting web page for the project. We have already created the web page with some content to get you started. We will use Bootstrap to style this web page, and learn Bootstrap features, classes and components along the way.
* Start your lite-server by typing **npm start** at the prompt. The index.html file should now be loaded into your default browser.

###  **Getting your Web page Bootstrap ready**

* Open the *index.html* file in your favourite text editor. If you are using Visual Studio Code, Brackets, Sublime Text or similar editors, you can open the project folder in the editor and then view index.html.
* Insert the following code in the `<head>` of *index.html* file before the title.

```html
<!-- Required meta tags always come first -->
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no">
    <meta http-equiv="x-ua-compatible" content="ie=edge">

    <!-- Bootstrap CSS -->
    <link rel="stylesheet" href="node_modules/bootstrap/dist/css/bootstrap.min.css">
```

* This will include Bootstrap CSS into your web page. Note the subtle change in the fonts of the content of the web page. This is the Bootstrap typography effect coming into play. The default Bootstrap typography sets the font to Helvetica Neue and selects the appropriate font size based on the choice of the heading style and paragraph style for the content.
* At the bottom of the page, just before the end of the body tag, add the following code to include the JQuery library, tether library and Bootstrap's Javascript plugins. Bootstrap by default uses the JQuery Javascript library for its Javascript plugins. Hence the need to include JQuery library in the web page.

```html
<!-- jQuery first, then Tether, then Bootstrap JS. -->
<script src="node_modules/jquery/dist/jquery.min.js"></script>
<script src="node_modules/tether/dist/js/tether.min.js"></script>
<script src="node_modules/bootstrap/dist/js/bootstrap.min.js"></script>
```

### **Bootstrap Grid System and Responsive Design**

Bootstrap is designed to be mobile first, meaning that the classes are designed such that we can begin by targeting mobile device screens first and then work upwards to larger screen sizes. The starting point for this is first through media queries. We have already added the support for media queries in the last lesson, where we added this line to the head:

`<meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no">`

The viewport meta tag ensures that the screen width is set to the device width and the content is rendered with this width in mind. This brings us to the second issue, designing the websites to be responsive to the size of the viewport. This is where the Bootstrap grid system comes to our aid. Bootstrap makes available four sizes, xs for extra small, sm for small, md for medium and lg for large screen sizes. We have already seen the basics of responsive design. In this exercise, we will employ the Bootstrap grid classes to design the websites. We would like our website to have the content stacked on extra small devices, but become horizontal within each row for smaller devices and beyond. Towards this goal, we will make use of the classes `.col-*`, `.col-sm-*`, `col-md-*`, and `.col-lg-*` for defining the layouts for the various device sizes. We can specify how many columns each piece of content will occupy within a row, all adding up to 12 or a multiple thereof.

###  **Using a Container class**

* We use the container class to keep content within a fixed width on the screen, determined by the size of the screen. The alternative is to use the container-fluid class to make the content automatically to span the full width of the screen. We will discuss further about this when we discuss the Bootstrap grid system in the next lecture. Add the container class to the first div right after the `</header>` in the file as follows.

`<div class="container"> ...`

###  **Dividing the content into rows**

* Let us now add the class row to the first-level inner *div* elements inside the container. This organizes the page into rows of content. In the next exercise, we will see how we can add other classes to the rows.

` <div class="row"> ...`

### **Creating a Jumbotron**

* Let us add the class jumbotron to the header class as shown below. This turns the header element into a Bootstrap component named Jumbotron. A jumbotron is used to showcase key content on a website. In this case we are using it to highlight the name of the restaurant.

` <header class="jumbotron"> ... `

* In the header add a **container** class to the first inner div and a row class to the second inner div.

###  **Creating a footer**

* Finally, in the footer add a **container** class to the first inner div and a row class to the second inner div.

### **Applying column classes within each row**

* In the header row, we will display the restaurant name and the description to occupy 8 columns, while we will leave four columns for displaying the restaurant logo in the future. Let us go into the jumbotron and define the classes for the inner divs as follows:

```html
<div class="col-12 col-sm-8"> ... </div>
<div class="col col-sm"> ... </div>
```

* For the remaining three div rows that contain content, let us define the classes for the inner divs as follows:

```html
<div class="col-sm-4 col-md-3"> ... </div>
<div class="col-sm col-md"> ... </div>
```

* For the footer, let us define the classes for the inner divs as follows:

```html
<div class="col-5 col-sm-2"> ... </div>
<div class="col-6 col-sm-5"> ... </div>
<div class="col col-sm-4"> ... </div>
<div class="col-auto"> ... </div>
```

Now you can see how the web page has been turned into a mobile-first responsive design layout.

### **Using Push, Pull and Offset with column layout classes**

* In the content rows, we would like to have the title and description to alternate so that it gives an interesting look to the web page. For extra small screens, the default stacked layout works best. This can be accomplished by using the .push-sm-* and .pull-sm-* for the first and the third rows as follows:

```html
<div class="col-sm-4 push-sm-8 col-md-3 push-md-9"> ... </div>
<div class="col-sm pull-sm-4 col-md pull-md-3"> ... </div>

```

* For the div containing the `<ul>` with the site links, update the class as follows:

`<div class="col-5 offset-1 col-sm-2">`

###  **Using Flex Order**

* Using Flex ordering, we can achieve the same effect that we achieved with the push and pull classes above. To do this, you can update the two div classes above as follows:

```html
<div class="col-sm-4 col-md-3 flex-last"> ... </div>
<div class="col-sm col-md flex-first"> ... </div>
```

###  **List styles**

* You can use several list styles to display lists in different formats. In this exercise, we will use the unordered list style *list-unstyled* to display the links at the bottom of the page without the bullets. To do this, go to the links in the footer and update the ul as follows

`<ul class="list-unstyled"> ... </ul>`

###  **Using Custom CSS classes**

* Create a folder named **css**. Then create a file named styles.css in the **css** folder. Open this file to edit the contents. Add the following CSS code to the file:

```css
.row-header{
    margin:0px auto;
    padding:0px;
}

.row-content {
    margin:0px auto;
    padding: 50px 0px 50px 0px;
    border-bottom: 1px ridge;
    min-height:400px;
}

.footer{
    background-color: #D1C4E9;
    margin:0px auto;
    padding: 20px 0px 20px 0px;
}
```

* Include the *styles.css* file into the head of the index.html file as follows:

`<link href="css/styles.css" rel="stylesheet">`

* Then add these classes to the corresponding rows in the *index.html* file as follows. See the difference in the index.html file in the browser. The first one is for the row in the `<header>`, the next three for the rows in the content, and the last one directly to the `<footer>` tag.

```html
<div class="row row-header"> ... </div>

<div class="row row-content"> ... </div>

<div class="row row-content"> ... </div>

<div class="row row-content"> ... </div>

<footer class="footer"> ... </footer>
```

* Our next set of customization is to the jumbotron and the address. Add the following to *styles.css* file:

```css
jumbotron {
    padding:70px 30px 70px 30px;
    margin:0px auto;
    background: #9575CD ;
    color:floralwhite;
}

address{
    font-size:80%;
    margin:0px;
    color:#0f0f0f;
}
```

###  **Vertically Centering the Content**

* In the content section, update all the rows as follows:

` <div class="row row-content align-items-center">`

* In the footer, update the third column div that contains the social media links as follows:

`<div class="col col-sm-4 align-self-center">`

###  **Horizontally Centering the Content**

* Update the copyright paragraph as follows:

```html
<div class="row justify-content-center">             
<div class="col-auto">
```

###  **Applying Inline CSS**

* Update the inner div containing the social media links as follows:

`<div style="text-align:center">`

#  **Assignment 1: Bootstrap and Responsive Design**

###  **Task 1**

In this task you will be updating the *aboutus.html* page to make use of the Bootstrap classes and components:

* Update the page to make use of the Bootstrap CSS classes.
* Update the page to also use your custom styles defined in your *styles.css* file, and
* Update the page to make use of all the Bootstrap JS components.

###  **Task 2**

In this task you will be adding appropriate formatting to the web page contents using container, row and column classes using the Bootstrap grid so that the web page is formatted to look like the figure given below.

* The "About Us" title should stretch the entire width of the row.
* The "Our History" part should occupy only half the width of the row for small to extra large screens, leaving space on the right side for more content to be added later. The content should be stacked for extra small screens.
* The "Corporate Leadership" section should stretch the entire width of the row.

![Web page for normal screen size](img/normal-size.png?raw=true "Web page for normal screen size")

###  **Task 3**

In this task you will use some responsive utilities provided by Bootstrap to hide some of the content only for extra small screens. You will make use of the `hidden-*` CSS classes provided by Bootstrap. To understand how to use these classes, please read the documentation here to learn how to apply the `hidden-*` classes. This will get you into the habit of consulting the Bootstrap documentation whenever you need to learn more about the various components and classes of Bootstrap. You should apply the classes so that the detailed descriptions of the corporate leadership is hidden only for extra small screens. Thus, your page should look like the figure below on extra small screens.

![Web page for extra small  screen size](img/hidden-xs-down.png?raw=true "Web page for extra small  screen size")

#  **Navbar and Breadcrumbs**

###  **Create a basic navigation bar**

* We will now add a simple navigation bar to the web page so that it provides links to the other pages on the website. Start by adding the following code to the body just above the header jumbotron.

```html
<nav class="navbar navbar-inverse navbar-toggleable-sm bg-primary fixed-top">
    <div class="container">
        <a class="navbar-brand" href="#">Ristorante Con Fusion</a>
            <ul class="navbar-nav">
                <li class="nav-item active"><a class="nav-link" href="#">Home</a></li>
                <li class="nav-item"><a class="nav-link" href="./aboutus.html">About</a></li>
                <li class="nav-item"><a class="nav-link" href="#">Menu</a></li>
                <li class="nav-item"><a class="nav-link" href="#">Contact</a></li>
            </ul>            
    </div>
</nav>
```

In the above code, we can see the use of the nav element to specify the navigation information for the website. This nav element is styled by the *navbar* that declares it as a navigation bar, and the *navbar-inverse* class to specify that the page should use the dark navigation bar. You will now notice the addition of a link with the name of the restaurant. This is the brand name for the website. You can replace this with the logo for the website. This is created by the `<a class="navbar-brand">` tag. In addition the inner ul is used to specify the items to be put in the navigation bar. This *ul* is styled with *navbar-nav* class to specify that the items should be displayed inline inside the navigation bar. We also use the container class inside the navigation bar.

###  **Creating a responsive navigation bar**

* We would like the navigation bar elements to collapse for shorter screens, to be replaced by a toggle button so that the items can be toggled on or off when required on small and extra small screens. This can be achieved by adding the following code to the navigation bar, just below the container div.

```html
<button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#Navbar">
    <span class="navbar-toggler-icon"></span>
</button>
```

This creates a button with three horizontal lines. For medium to extra large screens, this button is hidden. For small and extra small screens, this button becomes visible. This button will act as the toggle for the navbar items.

* To hide the items from the navigation bar for the small screens, we need to enclose the *ul* within another div as follows:

```html
<div class="collapse navbar-collapse" id="Navbar">
    <ul class="navbar-nav"> ... </ul>
</div>
```

By doing this, we are specifying that this div with *collapse* and *navbar-collapse* classes and with the id *Navbar* will be collapsed on small and xs screens, but can be toggled on or off when the toggle button is clicked. Note the use of `data-toggle="collapse" data-target="#Navbar"` within the button above. This specifies that the menu items are collapsed on small and xs screens when the toggle button is visible. They can be displayed or hidden by clicking the toggle button.

* Copy and paste the entire navbar code also into *aboutus.html* to add the navigation also to that page. Make sure to change the `<li>` corresponding to "About" to *active*, and remove the active class from the Home link. Also, update the home link to take you back to *index.html*. Update the navbar-brand tag also to take you back to *index.html*.

###  **Modifications to the CSS styles**

* We would like to have the navigation bar displayed in darker purple color, instead of the current color. In addition, when we use the fixed navigation bar, we should give the body of the page an upper margin of 50px, so that the top 50px of the page does not get hidden under the navigation bar. We accomplish these by adding these CSS customisations to the *styles.css* file

```css
body{
    padding:50px 0px 0px 0px;
    z-index:0;
}

.navbar-inverse {
     background-color: #512DA8;
}
```

* Remember to delete the *bg-primary* class from the `<nav>` element in both *index.html* and *aboutus.html*.

###  **Adding Breadcrumbs**

* To add breadcrumbs to our pages, we take the help of the breadcrumb and breadcrumb-item classes to add the following to the row containing the About Us title in *aboutus.html*.

```html
<ol class="col-12 breadcrumb">
    <li class="breadcrumb-item"><a href="./index.html">Home</a></li>
    <li class="breadcrumb-item active">About Us</li>
</ol>
```

#  **Icon Fonts**

###  **Using Icon Fonts and Other CSS classes**

* One of the most popular icon font toolkit is Font Awesome. Go to its website http://fontawesome.io/ to check out more details about this icon font. You can get Font Awesome using npm by typing the following at the prompt:

`npm install font-awesome --save`

* Download the bootstrap-social.css file given below to *conFusion/css* folder. This is a modified version of the bootstrap-social available on the http://lipis.github.io/bootstrap-social/. We added in support for G+ and YouTube buttons.

* We now need to include the CSS files for font awesome and bootstrap-social in the index.html file. Add the following code to the head of the file after the links for importing Bootstrap CSS classes:

```html
<link rel="stylesheet" href="node_modules/font-awesome/css/font-awesome.min.css">
<link rel="stylesheet" href="css/bootstrap-social.css">
```

* Let us now use some font icons in our web page and decorate it. Update the navbar's ul list items as follows in index.html:

```html
 <li class="nav-item active">
     <a class="nav-link" href="#"><span class="fa fa-home fa-lg"></span> Home</a>
 </li>
<li class="nav-item">
    <a class="nav-link" href="./aboutus.html"><span class="fa fa-info fa-lg"></span> About</a>
</li>
<li class="nav-item">
    <a class="nav-link" href="#"><span class="fa fa-list fa-lg"></span> Menu</a>
</li>
<li class="nav-item">
    <a class="nav-link" href="#"><span class="fa fa-address-card fa-lg"></span> Contact</a>
</li>
```
* Similarly update the navbar's ul list items as follows in aboutus.html:

```html
<li class="nav-item">
    <a class="nav-link" href="./index.html"><span class="fa fa-home fa-lg"></span> Home</a>
</li>
<li class="nav-item active">
    <a class="nav-link" href="#"><span class="fa fa-info fa-lg"></span> About</a>
</li>
<li class="nav-item">
    <a class="nav-link" href="#"><span class="fa fa-list fa-lg"></span> Menu</a>
</li>
<li class="nav-item">
    <a class="nav-link" href="#"><span class="fa fa-address-card fa-lg"></span> Contact</a>
</li>
```
* Next, in both index.html and aboutus.html, go down to the address in the footer of the page and replace the "Tel.", "Fax" and "Email" with the corresponding font awesome based icons as follows:

```html
<i class="fa fa-phone fa-lg"></i>: +852 1234 5678<br>
<i class="fa fa-fax fa-lg"></i>: +852 8765 4321<br>
<i class="fa fa-envelope fa-lg"></i>: <a href="mailto:confusion@food.net">confusion@food.net</a>
```
* Finally, let us use the bootstrap-social CSS classes to create the social buttons in the footer in both index.html and aboutus.html, by replacing the social sites' links with the following code:

```html
 <div style="text-align:center">
    <a class="btn btn-social-icon btn-google-plus" href="http://google.com/+">
        <i class="fa fa-google-plus"></i>
    </a>
    <a class="btn btn-social-icon btn-facebook" href="http://www.facebook.com/profile.php?id=">
        <i class="fa fa-facebook"></i>
    </a>
    <a class="btn btn-social-icon btn-linkedin" href="http://www.linkedin.com/in/">
        <i class="fa fa-linkedin"></i>
    </a>
    <a class="btn btn-social-icon btn-twitter" href="http://twitter.com/">
        <i class="fa fa-twitter"></i>
    </a>
    <a class="btn btn-social-icon btn-youtube" href="http://youtube.com/">
        <i class="fa fa-youtube"></i>
    </a>
    <a class="btn btn-social-icon" href="mailto:">
        <i class="fa fa-envelope-o"></i>
    </a>
</div>
```

#  **Buttons**

###  **Adding a Button Bar**

* We are now going to add content to *contactus.html* file to learn more about buttons and button bars. Go to the div where we specify "Button group goes here", and replace it with the following code to create a button bar containing three buttons:

```html
 <div class="btn-group" role="group">
    <a role="button" class="btn btn-primary" href="tel:+85212345678"><i class="fa fa-phone"></i> Call</a>
    <a role="button" class="btn btn-info"><i class="fa fa-skype"></i> Skype</a>
    <a role="button" class="btn btn-success" href="mailto:confusion@food.net"><i class="fa fa-envelope-o"></i> Email</a>
</div>
```

Note how we define the button bar using the *btn-group* class, and then add the three buttons using the `<a>` tag. In this case, the three buttons are hyperlinks that cause an action and have an href associated with them. So we decided to use the `<a>` tag instead of the `<button>` tag. Note how the `<a>` tags have been styled using the *btn* class.


