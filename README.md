#  **Ristorant ConFusion**

### Some Global Configuration for Git

* To configure your user name to be used by Git, type the following at the prompt:

`git config --global user.name "Your Name"`

* To configure your email to be used by Git, type the following at the prompt:

`git config --global user.email <your email address>`

* You can check your default Git global configuration, you can type the following at the prompt:

`git config --list`

## **Basics of Node.js and NPM**

### Initializing package.json

* At the command prompt in your project folder, type:

`npm init`

* Follow along the prompts and answer the questions as follows: accept the default values for most of the entries, except set the entry point to index.html

* This should create a *package.json* file in your project folder.

### Installing an NPM Module

* Install an NPM module, lite-server, that allows you to run a Node.js based development web server and serve up your project files. To do this, type the following at the prompt:

`npm install lite-server --save-dev`

* Next, open package.json in your editor and modify it as shown below. Note the addition of two lines, line 7 and line 9.

```json
{
  "name": "git-test",
  "version": "1.0.0",
  "description": "This is the Git and Node basic learning project",
  "main": "index.html",
  "scripts": {
    "start": "npm run lite",
    "test": "echo \"Error: no test specified\" && exit 1",
    "lite": "lite-server"
  },
  "repository": {
    "type": "git",
    "url": "git+https://jogesh_k_muppala@bitbucket.org/jogesh_k_muppala/git-test.git"
  },
  "author": "",
  "license": "ISC",
  "homepage": "https://bitbucket.org/jogesh_k_muppala/git-test#readme",
  "devDependencies": {
    "lite-server": "^2.2.2"
  }
}
```

* Next, start the development server by typing the following at the prompt:

`npm start`

* This should open your `index.html` page in your default browser.

* If you now open the `index.html` page in an editor and make changes and save, the browser should immediately refresh to reflect the changes.

### Setting up .gitignore

* Next, create a file in your project directory named *.gitignore* (**Note**: the name starts with a period)Then, add the following to the .gitignore file:

`node_modules`

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

### **List styles**

* You can use several list styles to display lists in different formats. In this exercise, we will use the unordered list style *list-unstyled* to display the links at the bottom of the page without the bullets. To do this, go to the links in the footer and update the ul as follows

`<ul class="list-unstyled"> ... </ul>`

### **Using Custom CSS classes**

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

### **Vertically Centering the Content**

* In the content section, update all the rows as follows:

` <div class="row row-content align-items-center">`

* In the footer, update the third column div that contains the social media links as follows:

`<div class="col col-sm-4 align-self-center">`

### **Horizontally Centering the Content**

* Update the copyright paragraph as follows:

```html
<div class="row justify-content-center">             
<div class="col-auto">
```

### **Applying Inline CSS**

* Update the inner div containing the social media links as follows:

`<div style="text-align:center">`

# **Assignment 1: Bootstrap and Responsive Design**

### **Task 1**

In this task you will be updating the *aboutus.html* page to make use of the Bootstrap classes and components:

* Update the page to make use of the Bootstrap CSS classes.
* Update the page to also use your custom styles defined in your *styles.css* file, and
* Update the page to make use of all the Bootstrap JS components.

### **Task 2**

In this task you will be adding appropriate formatting to the web page contents using container, row and column classes using the Bootstrap grid so that the web page is formatted to look like the figure given below.

* The "About Us" title should stretch the entire width of the row.
* The "Our History" part should occupy only half the width of the row for small to extra large screens, leaving space on the right side for more content to be added later. The content should be stacked for extra small screens.
* The "Corporate Leadership" section should stretch the entire width of the row.

![Web page for normal screen size](img/normal-size.png?raw=true "Web page for normal screen size")

### **Task 3**

In this task you will use some responsive utilities provided by Bootstrap to hide some of the content only for extra small screens. You will make use of the `hidden-*` CSS classes provided by Bootstrap. To understand how to use these classes, please read the documentation here to learn how to apply the `hidden-*` classes. This will get you into the habit of consulting the Bootstrap documentation whenever you need to learn more about the various components and classes of Bootstrap. You should apply the classes so that the detailed descriptions of the corporate leadership is hidden only for extra small screens. Thus, your page should look like the figure below on extra small screens.

![Web page for extra small  screen size](img/hidden-xs-down.png?raw=true "Web page for extra small  screen size")

# **Navbar and Breadcrumbs**

### **Create a basic navigation bar**

* We will now add a simple navigation bar to the web page so that it provides links to the other pages on the website. Start by adding the following code to the body just above the header jumbotron.

```html
<nav class="navbar navbar-dark navbar-expand-sm bg-primary fixed-top">
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

### **Creating a responsive navigation bar**

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

### **Modifications to the CSS styles**

* We would like to have the navigation bar displayed in darker purple color, instead of the current color. In addition, when we use the fixed navigation bar, we should give the body of the page an upper margin of 50px, so that the top 50px of the page does not get hidden under the navigation bar. We accomplish these by adding these CSS customisations to the *styles.css* file

```css
body{
    padding:50px 0px 0px 0px;
    z-index:0;
}

.navbar-dark {
     background-color: #512DA8;
}
```

* Remember to delete the *bg-primary* class from the `<nav>` element in both *index.html* and *aboutus.html*.

### **Adding Breadcrumbs**

* To add breadcrumbs to our pages, we take the help of the breadcrumb and breadcrumb-item classes to add the following to the row containing the About Us title in *aboutus.html*.

```html
<ol class="col-12 breadcrumb">
    <li class="breadcrumb-item"><a href="./index.html">Home</a></li>
    <li class="breadcrumb-item active">About Us</li>
</ol>
```

# **Icon Fonts**

### **Using Icon Fonts and Other CSS classes**

* One of the most popular icon font toolkit is Font Awesome. Go to its website http://fontawesome.io/ to check out more details about this icon font. You can get Font Awesome using npm by typing the following at the prompt:

`npm install font-awesome --save`

* Another module that we install is Bootstrap Social that enables the addition of Social buttons to our site. You can find more information about it at https://lipis.github.io/bootstrap-social/. To install it using npm, type the following at the prompt:

`npm i bootstrap-social --save`

* We now need to include the CSS files for font awesome and bootstrap-social in the index.html file. Add the following code to the head of the file after the links for importing Bootstrap CSS classes. Do the same change to aboutus.html file:

```html
<link rel="stylesheet" href="node_modules/font-awesome/css/font-awesome.min.css">
<link rel="stylesheet" href="node_modules/bootstrap-social/bootstrap-social.css">
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

# **Buttons**

### **Adding a Button Bar**

* We are now going to add content to *contactus.html* file to learn more about buttons and button bars. Go to the div where we specify "Button group goes here", and replace it with the following code to create a button bar containing three buttons:

```html
 <div class="btn-group" role="group">
    <a role="button" class="btn btn-primary" href="tel:+85212345678"><i class="fa fa-phone"></i> Call</a>
    <a role="button" class="btn btn-info"><i class="fa fa-skype"></i> Skype</a>
    <a role="button" class="btn btn-success" href="mailto:confusion@food.net"><i class="fa fa-envelope-o"></i> Email</a>
</div>
```

Note how we define the button bar using the *btn-group* class, and then add the three buttons using the `<a>` tag. In this case, the three buttons are hyperlinks that cause an action and have an href associated with them. So we decided to use the `<a>` tag instead of the `<button>` tag. Note how the `<a>` tags have been styled using the *btn* class.

# **Forms**

### **Adding a Basic Form**

Add the following code to page to create a simple horizontal form with two fields:

```html
<form>
    <div class="form-group row">
        <label for="firstname" class="col-md-2 col-form-label">First Name</label>
        <div class="col-md-10">
            <input type="text" class="form-control" id="firstname" name="firstname" placeholder="First Name">
        </div>
    </div>
    <div class="form-group row">
        <label for="lastname" class="col-md-2 col-form-label">Last Name</label>
        <div class="col-md-10">
            <input type="text" class="form-control" id="lastname" name="lastname" placeholder="Last Name">
        </div>
    </div>
</form>
```

This creates a form with two elements in the form. Note that the class *row* in the form enables us to use the Bootstrap grid system. Hence we can style the contents using the column classes as appropriate.

### **Adding a Input Group with addons**

* We now see the use of an input-group together with input-group-addons. Let us add fields to seek user's telephone number and email:

```html
<div class="form-group row">
    <label for="telnum" class="col-12 col-md-2 col-form-label">Contact Tel.</label>
    <div class="col-5 col-sm-4 col-md-3">
        <div class="input-group">
            <div class="input-group-addon">(</div>
            <input type="tel" class="form-control" id="areacode" name="areacode" placeholder="Area code">
            <div class="input-group-addon">)</div>
        </div>
    </div>
    <div class="col-7 col-sm-6 col-md-7">
        <input type="tel" class="form-control" id="telnum" name="telnum" placeholder="Tel. number">
    </div>
</div>
<div class="form-group row">
    <label for="emailid" class="col-md-2 col-form-label">Email</label>
    <div class="col-md-10">
        <input type="email" class="form-control" id="emailid" name="emailid" placeholder="Email">
    </div>
</div>
```
Note the use of the *input-group* and *input-group-addon* classes.

### **Adding a Checkbox and Select**

* We now see the addition of a checkbox and a select element to the form. Note the styling of these elements using Bootstrap classes:

```html
<div class="form-group row">
    <div class="form-check col-md-6 offset-md-2">
        <label class="form-check-label">
            <input type="checkbox" class="form-check-input" name="approve" value="">
            <strong>May we contact you?</strong>
        </label>
    </div>
    <div class="col-md-3 offset-md-1">
        <select class="form-control">
            <option>Tel.</option>
            <option>Email</option>
        </select>
    </div>
</div>
```
### **Adding a textarea**

* Next we add a textarea for the users to submit their feedback comments as follows:
* 
```html
<div class="form-group row">
    <label for="feedback" class="col-md-2 col-form-label">Your Feedback</label>
    <div class="col-md-10">
        <textarea class="form-control" id="feedback" name="feedback" rows="12"></textarea>
    </div>
</div>
```

### **Adding the Submit Button**

* Finally, we add the submit button to the form as follows:

```html
<div class="form-group row">
    <div class="offset-md-2 col-md-10">
        <button type="submit" class="btn btn-primary">Send Feedback</button>
    </div>
</div>
```

# **Displaying Content: Tables and Cards**

### **Bootstrap Tables**

* In this part, we will add a new row of content after the Corparate Leadership row in the page. We first start by adding a row and columns to the page as follows:

```html
<div class="row row-content">
    <div class="col-12 col-sm-9">
        <h2>Facts &amp; Figures</h2>
    </div>
    <div class="col-12 col-sm-3">
    </div>
</div> 
```
* Inside the first column of this row, insert the table as follows:

```html
<div class="table-responsive">
    <table class="table table-striped">
        <thead class="thead-inverse">
            <tr>
                <th>&nbsp;</th>
                <th>2013</th>
                <th>2014</th>
                <th>2015</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <th>Employees</th>
                <td>15</td>
                <td>30</td>
                <td>40</td>
            </tr>
            <tr>
                <th>Guests Served</th>
                <td>15000</td>
                <td>45000</td>
                <td>100,000</td>
            </tr>
            <tr>
                <th>Special Events</th>
                <td>3</td>
                <td>20</td>
                <td>45</td>
            </tr>
            <tr>
                <th>Annual Turnover</th>
                <td>$251,325</td>
                <td>$1,250,375</td>
                <td>~$3,000,000</td>
            </tr>
        </tbody>
    </table>
</div>
```
Note the use of *table-responsive* class to create a responsive table, and the *table-striped* and *thead-inverse* classes for styling the table.

### **Bootstrap Cards**

* Next we add a card to the second div in the first content row as follows, updating the div first by adding the classes col-12 col-sm-6 to it and then adding the card:

```html
<div class="col-12 col-sm-6">
    <div class="card">
        <h3 class="card-header bg-primary text-white">Facts At a Glance</h3>
        <div class="card-block">
            <dl class="row">
                <dt class="col-6">Started</dt>
                <dd class="col-6">3 Feb. 2013</dd>
                <dt class="col-6">Major Stake Holder</dt>
                <dd class="col-6">HK Fine Foods Inc.</dd>
                <dt class="col-6">Last Year's Turnover</dt>
                <dd class="col-6">$1,250,375</dd>
                <dt class="col-6">Employees</dt>
                <dd class="col-6">40</dd>
            </dl>
        </div>
    </div>
</div>
```
* Next, we add a Bootstrap card and include a quotation in the card using the blockquote typography style:

```html
 <div class="col-12">
    <div class="card card-block bg-faded">
        <blockquote class="blockquote">
            <p class="mb-0">You better cut the pizza in four pieces because
                            I'm not hungry enough to eat six.</p>
            <footer class="blockquote-footer">Yogi Berra,
                <cite title="Source Title">
                    The Wit and Wisdom of Yogi Berra, P. Pepe, Diversion Books, 2014
                </cite>
            </footer>
        </blockquote>
    </div>
</div>
```

Note the use of the `<blockquote>` tag to create a block quote in the card. We can use a `<footer>` inside the block quote to specify the attribution of the quote to its origin.

# **Images and Media**

### **Adding the Restaurant Logo**

* We will now add the restaurant logo to the Jumbotron. In index.html go to the header row inside the jumbotron and replace the second `<div>` column with the following code:

```html
<div class="col col-sm align-self-center">
    <img src="img/logo.png" class="img-fluid">
</div>
```

* Next, we will add the logo to the navbar where we display the restaurant brand. Go to the navbar and replace the code there for the `<a>` tag with the "navbar-brand" class with the following code:

```html
<a class="navbar-brand" href="#"><img src="img/logo.png" height="30" width="41"></a>
```
* Repeat the above two steps for the *aboutus.html* and the *contactus.html* page also to update their navbars and jumbotrons.

### **Adding Media Objects**

* Next we will work with the content on the web page and use the media object classes to style the content in the content rows.

* Go to the first content row, and replace the content in the second column containing the description of Uthappizza with the following code:

```html
<div class="media">
    <img class="d-flex mr-3 img-thumbnail align-self-center" src="img/uthappizza.png" alt="Uthappizza">
    <div class="media-body">
        <h2 class="mt-0">Uthappizza</h2>
        <p class="hidden-xs-down">A unique combination of Indian Uthappam (pancake) and Italian pizza, topped with Cerignola olives, ripe vine cherry tomatoes, Vidalia onion, Guntur chillies and      Buffalo Paneer.
        </p>
    </div>
</div>
```

* Next, we will go to the third row and replace the contents of the second column containing the description about Alberto with the following content:

```html
 <div class="media">
    <img class="d-flex mr-3 img-thumbnail align-self-center" src="img/alberto.png" alt="Alberto Somayya">
    <div class="media-body">
        <h2 class="mt-0">Alberto Somayya</h2>
        <h4>Executive Chef</h4>
        <p class="hidden-xs-down">Award winning three-star Michelin chef with wide                          International experience having worked closely with whos-who in the culinary world, he specializes in
        creating mouthwatering Indo-Italian fusion experiences.
        </p>
    </div>
</div>
```
# **Alerting Users**

### **Adding Badges**

* We will continue to edit the *index.html* file. In this file, we will add a badge *HOT* next to the name of the dish Uthappizza in the first content row. To do this, add the following code inside the `<h2>` containing the name of the dish:

```html
<span class="badge badge-danger">HOT</span>
```

* Next we will add a badge as a badge-pill right next to the earlier tag in the web page. Add the following code to the `<h2>` tag:

```html
<span class="badge badge-pill badge-default">$4.99</span>
```

# **Tabs**

### **Adding Tab Navigation Elements**

* Open the *aboutus.html* page and move to the second content row containing the details of the corporate leadership of the restaurant.
* Right after the Corporate Leadership heading, introduce the following code to set up the tabbed navigation:

```html
<ul class="nav nav-tabs">
    <li class="nav-item">
        <a class="nav-link active" href="#peter" role="tab" data-toggle="tab">Peter Pan, CEO</a>
    </li>
    <li class="nav-item">
        <a class="nav-link" href="#danny" role="tab" data-toggle="tab">Danny Witherspoon, CFO</a>
    </li>
    <li class="nav-item">
        <a class="nav-link" href="#agumbe"role="tab" data-toggle="tab">Agumbe Tang, CTO</a>
    </li>
    <li class="nav-item">
        <a class="nav-link" href="#alberto" role="tab" data-toggle="tab">Alberto Somayya, Exec. Chef</a>
    </li>
</ul>
```

Note the use of the `<ul>` tag with the nav and *nav-tabs* classes to set up the tab navigation. Each list item within the list acts as the tab element. Within each list item, note that we set up the `<a>` tags with the *href* pointing to the *id* of the tab pane of content to be introduced later. Also note that the `<a>` tag contains the *data-toggle=tab* attribute. The first list element's `<a>` tag contains the class active. This tab will be the open tab when we view the web page. We can switch to the other tabs using the tabbed navigation that we just set up.

### **Adding Tab Content**

* The details about the various corporate leaders should now be organized into various tab panes. To begin this, we will enclose the entire content into a div element with the class tab-content as specified below:

```html
<div class="tab-content">
    ...
</div>
```

* Then we take the name and description of the CEO of the company and enclose it within a tab-pane as follows

```html
<div role="tabpanel" class="tab-pane fade show active" id="peter">
    <h3>Peter Pan <small>Chief Epicurious Officer</small></h3>
    <p> ... </p>
</div>
```

Note the use of the *tab-pane*, *fade*, *show*, and *active* classes and with *peter* as the id. This is the same id used as the *href* in the `<a>` link in the navigation.

* The remaining content is also similarly enclosed inside appropriate divs with the correct ids and the classes specified as above. Only the first tab pane will have the *show* and *active* classes specified to indicate that the content should be visible on the web page by default.

### **Modifying the tab-content CSS**

* We now modify the CSS styles for the tab-content class in the mystyles.css file as follows:


```css
.tab-content {
    border-left: 1px solid #ddd;
    border-right: 1px solid #ddd;
    border-bottom: 1px solid #ddd;
    padding: 10px;
}
```
This modification adds a 1px border to the tab content which joins with the upper border introduced by the tab navigation element to give a clean tab like appearance.

# **Converting Tabs to Accordion**

* First delete the `<ul>` class that was introduced for the tabbed navigation.
* Then the turn the *tab-content* div into a *accordion div*. Use the code structure as shown below:

```html
<div id="accordion" role="tablist">
    . . .
</div>
```

* Then, convert the first tab-pane into a card such that the name appears as a card heading, and the `<p>` will be in the card body. Use the structure of the code as shown below:

```html
<div class="card">
    <div class="card-header" role="tab" id="peterhead">
        <h3 class="mb-0">
            <a data-toggle="collapse" data-parent="#accordion" href="#peter">
                Peter Pan <small>Chief Epicurious Officer</small>
            </a>
        </h3>
    </div>
    <div role="tabpanel" class="collapse show" id="peter">
        <div class="card-block">
            <p class="hidden-xs-down">. . .</p>
        </div>
    </div>
</div>
```

* For the remaining three leaders, use the same structure as above, with the appropriate ids set up for the cards, as shown in the code structure below:

```html
<div class="card">
    <div class="card-header" role="tab" id="dannyhead">
        <h3 class="mb-0">
            <a class="collapsed" data-toggle="collapse" data-parent="#accordion" href="#danny">
                Dhanasekaran Witherspoon <small>Chief Food Officer</small>
            </a>
        </h3>
    </div>
    <div role="tabpanel" class="collapse" id="danny">
        <div class="card-block">
            <p class="hidden-xs-down">. . .</em></p>
        </div>
    </div>
</div>
<div class="card">
    <div class="card-header" role="tab" id="agumbehead">
        <h3 class="mb-0">
            <a class="collapsed" data-toggle="collapse" data-parent="#accordion" href="#agumbe">
                Agumbe Tang <small>Chief Taste Officer</small>
            </a>
        </h3>
    </div>
    <div role="tabpanel" class="collapse" id="agumbe">
        <div class="card-block">
            <p class="hidden-xs-down">. . .</em></p>
        </div>
    </div>
</div>
<div class="card">
    <div class="card-header" role="tab" id="albertohead">
        <h3 class="mb-0">
            <a class="collapsed" data-toggle="collapse" data-parent="#accordion" href="#alberto">
                Alberto Somayya <small>Executive Chef</small>
            </a>
        </h3>
    </div>
    <div role="tabpanel" class="collapse" id="alberto">
        <div class="card-block">
            <p class="hidden-xs-down">. . .</em></p>
        </div>
    </div>
</div>
```

# **Tooltips and Modals**

### **Adding a Tooltip**

* Let us now switch to the *index.html* page. We will now add a tooltip to this page. The tooltip will be added to the "Reserve Table" button that is in the jumbotron. We will update the `<a>` tag for the button as follows:

```html
<a type="button" class="btn btn-warning btn-sm btn-block" data-toggle="tooltip" data-html="true"  
   title="Or Call us at  <br><strong>+852 12345678</strong>" data-placement="bottom" href="#reserveform">
```

As you can see from the code, we add a **data-toggle**, **data-placement** and a **title** attribute to the `<a>` tag in order to introduce a tooltip.

* The tooltip needs to be activated by adding a small Javascript code to the bottom of the page as follows:

```html
<script>
    $(document).ready(function(){
        $('[data-toggle="tooltip"]').tooltip();
    });
</script>
```

This script is added right after the line that imports the bootstrap.min.js file.

### **Adding a Modal**

* In the next step we introduce the modal to the web page. To set up the modal, add the following code right after the navbar at the top of the page.

```html
<div id="loginModal" class="modal fade" role="dialog">
    <div class="modal-dialog modal-lg" role="content">
        <!-- Modal content-->
        <div class="modal-content">
            <div class="modal-header">
                <h4 class="modal-title">Login </h4>
                <button type="button" class="close" data-dismiss="modal">&times;</button>
            </div>
            <div class="modal-body">
                <form class="form-inline">
                    <div class="form-group">
                        <label class="sr-only" for="exampleInputEmail3">Email address</label>
                        <input type="email" class="form-control form-control-sm mr-1" id="exampleInputEmail3" placeholder="Enter email">
                    </div>
                    <div class="form-group">
                        <label class="sr-only" for="exampleInputPassword3">Password</label>
                        <input type="password" class="form-control form-control-sm mr-1" id="exampleInputPassword3" placeholder="Password">
                    </div>
                    <div class="form-check">
                        <label class="form-check-label">
                            <input class="form-check-input" type="checkbox"> Remember me
                        </label>
                    </div>
                </form>
            </div>
            <div class="modal-footer">
                <button type="button" class="btn btn-default btn-sm" data-dismiss="modal">Cancel</button>
                <button type="submit" class="btn btn-primary btn-sm">Sign in</button>
            </div>
        </div>
    </div>
</div>
```

* Next we introduce another link on the right side of the navbar in order to trigger the display of the modal. To do this, add the following code in the navbar after the `</ul>`:

```html
<span class="navbar-text">
    <a data-toggle="modal" data-target="#loginModal">
    <span class="fa fa-sign-in"></span> Login</a>
</span>
```

* In addition, add the *mr-auto* class to the `<ul>` in the navbar as follows:
]
```html
<ul class="navbar-nav mr-auto">`
```
We are introducing another link to the right of the navbar using the *navbar-text* and using the *mr-auto* class to the `<ul>` as shown above. This contains a link with an `<a>` tag with the *data-toggle="modal"* and *data-target="#loginModal"* attributes.

# **Carousel**

### **Adding a row for the carousel**

* The carousel will be added to the *index.html* page. In this page, go to the top of the container div that contains the content of the page and add a new content row and an inner div spanning all the 12 columns as follows:

```html
<div class="row row-content">
    <div class="col">
    </div>
</div>
```
### **Adding a Carousel**

* Next, add the basic carousel div inside the content row that you just added as follows:

```html
<div id="mycarousel" class="carousel slide" data-ride="carousel">
</div>
```

### **Adding Carousel Content**

* Next add the content inside the carousel as follows:

```html
<div class="carousel-inner" role="listbox">
    <div class="carousel-item active">
        <img class="d-block img-fluid" src="img/uthappizza.png" alt="Uthappizza">
        <div class="carousel-caption d-none d-md-block">
            <h2>Uthappizza <span class="badge badge-danger">HOT</span> <span class="badge badge-pill badge-default">$4.99</span></h2>
            . . .
        </div>
    </div>
    <div class="carousel-item">
        . . .
    </div>
    <div class="carousel-item">
    . . .
    </div>
</div>
```
### **Adding CSS Classes**

* Add the following CSS classes to the *mystyles.css* file:

```css
.carousel {
    background:#512DA8;
}
.carousel-item {
    height: 300px;
}
.carousel-item img {
    position: absolute;
    top: 0;
    left: 0;
    min-height: 300px;
}
```

### **Adding Carousel Controls**

* Next, we will add manual controls to the carousel so that we can manually move among the slides. Add the following code to the bottom after the carousel items in the div of the carousel to add slide indicators that enable us to select a specific slide:

```html
<ol class="carousel-indicators">
    <li data-target="#mycarousel" data-slide-to="0" class="active"></li>
    <li data-target="#mycarousel" data-slide-to="1"></li>
    <li data-target="#mycarousel" data-slide-to="2"></li>
</ol>
```

* Then, add the left and right controls to the carousel that enable us to move to the previous and next slide manually. Add this to the bottom of the carousel div:

```html
<a class="carousel-control-prev" href="#mycarousel" role="button" data-slide="prev">
    <span class="carousel-control-prev-icon"></span>
</a>
<a class="carousel-control-next" href="#mycarousel" role="button" data-slide="next">
    <span class="carousel-control-next-icon"></span>
</a>
```

# **Assignment 3: Bootstrap JavaScript Components**

### **Task 1**

In this task you will move the table reservation form from the last content row into a modal. You should also remove the last content row.

* The form should be completely shifted to a modal.
* Add a Cancel button in the form that will dismiss the modal when clicked.
* The modal header should contain a X button to dismiss the modal.

### **Task 2**

In this task you will be adding a radio button group to the form to allow the selection of the smoking/non-smoking section of the restaurant.

* The radio button group should start out with the non-smoking section selected by default.
* The row containing the button group will have the label Section displayed preceding it in the form.

### **Task 3**

In this task you will be updating the Reserve Table button in the Jumbotron:

* Remove the tooltip from the button. This is to facilitate the button to be used to trigger the modal containing the table reservation form in the later tasks. A single button can support only one Javascript plugin via the data-* attributes. Make sure to remove the JavaScript script at the bottom of the page. Also remove the corresponding JavaScript code for the tooltip from the bottom of the page.
* You will update the Reserve Table button to show the modal containing the table reservation form when the button is clicked.

At the end of this assignment, your index.html file should look like this:

![Modal to reserve table](img/modal-reserve-table.png?raw=true "Modal to reserve table")

# **Bootstrap and JQuery**

### **Adding the Carousel Control Buttons**

We will introduce two new buttons into the carousel component that we already included in the index.html page. To add the two buttons to the carousel, add the following code to the end of the carousel:

```html
<div class="btn-group" id="carouselButtons">
    <button class="btn btn-danger btn-sm" id="carousel-pause">
        <span class="fa fa-pause"></span>
    </button>
    <button class="btn btn-danger btn-sm" id="carousel-play">
        <span class="fa fa-play"></span>
    </button>
</div>
```
We are adding the two buttons inside a button group with the ID carouselButtons. The two buttons contain the pause and play glyphicons to indicate their corresponding actions.

### **Adding CSS Class for the Buttons**

* Next, we add the following CSS class to styles.css file to position the buttons at the bottom-right corner of the carousel:

```css
#carouselButtons {
    right:0px;
    position: absolute;
    bottom: 0px;
}
```

### **Adding JavaScript Code**

* Finally we add the following JavaScript code to activate the buttons:

```html
<script>
    $(document).ready(function(){
        $("#mycarousel").carousel( { interval: 2000 } );
        $("#carousel-pause").click(function(){
            $("#mycarousel").carousel('pause');
        });
        $("#carousel-play").click(function(){
            $("#mycarousel").carousel('cycle');
        });
    });
</script>
```

### **Modifying the Carousel Control Buttons**

* We will modify the carousel control buttons in the carousel component that we already included in the index.html page. Instead of two buttons, we will use a single button that will indicate if the carousel is currently cycling or paused. Furthermore we can use the button to toggle the carousel cycling behavior:

```html
<button class="btn btn-danger btn-sm" id="carousel-button">
    <span id="carousel-button-icon" class="fa fa-pause"></span>
</button>
```

#### **Modifying CSS Class for the Button**

* Next, we add the following CSS class to styles.css file to position the button at the bottom-right corner of the carousel:

```css
#carousel-button {
    right:0px;
    position: absolute;
    bottom: 0px;
}
```

### **Modifying JavaScript Code**

* Finally we modify the JavaScript code to control the behavior of the carousel and also show the appropriate button:

```javascript
$("#carousel-button").click(function(){
    if ($("#carousel-button").children("span").hasClass('fa-pause')) {
        $("#mycarousel").carousel('pause');
        $("#carousel-button").children("span").removeClass('fa-pause');
        $("#carousel-button").children("span").addClass('fa-play');
    }
    else if ($("#carousel-button").children("span").hasClass('fa-play')){
        $("#mycarousel").carousel('cycle');
        $("#carousel-button").children("span").removeClass('fa-play');
        $("#carousel-button").children("span").addClass('fa-pause');          
    }
});
```
# **Less**

### **Adding Less Variables**

* Open the *conFusion* project in a text editor of your choice. In the css folder, create a file named *styles.less*. We will add the Less code into this file.
* Add the following Less variables into the file:

```less
@lt-gray: #ddd;
@background-dark: #512DA8;
@background-light: #9575CD;
@background-pale: #D1C4E9;

// Height variables
@carousel-item-height: 300px;
```

### **Less Mixins**

* Next we add a mixin into the file as follows:

```less
zero-margin (@pad-up-dn: 0px, @pad-left-right: 0px) {
	margin:0px auto;
	padding: @pad-up-dn @pad-left-right;
}
```
We will make use of this to define several row classes next.

* Using the variables and Mixin class that we defined earlier, add the following row classes to the file:

```less
.row-header {
    .zero-margin();
}

.row-content {
    .zero-margin(50px,0px);
    border-bottom: 1px ridge;
    min-height:400px;
}

.footer {
    background-color: @background-pale;
    .zero-margin(20px, 0px);
}

.jumbotron {
    .zero-margin(70px,30px);
    background: @background-light ;
    color:floralwhite;
}

address {
    font-size:80%;
    margin:0px;
    color:#0f0f0f;
}

body {
    padding:50px 0px 0px 0px;
    z-index:0;
}

.navbar-inverse {
     background-color: @background-dark;
}
.tab-content {
    border-left: 1px solid @lt-gray;
    border-right: 1px solid @lt-gray;
    border-bottom: 1px solid @lt-gray;
    padding: 10px;
}
```
Note the use of the variables and the mixin with various parameters in defining the classes.

### **Nesting Selectors**

* Next we add a carousel class to illustrate the use of nesting of classes in Less, as follows:

```less
carousel {
    background:@background-dark;

    .carousel-item {
        height: @carousel-item-height;
        img {
            position: absolute;
            top: 0;
            left: 0;
            min-height: 300px;
        }
    }
}

#carousel-button {
    right:0px;
    position: absolute;
    bottom: 0px;
}
```

### **Installing and using the lessc Compiler**

Now we install the node module to support the compilation of the Less file. To do this, type the following at the command prompt:

`npm install -g less`

This will install the *less* NPM module globally so that it can be used by any project. **Note: if you are executing this on a Mac or Linux machine, you may need to add "sudo" to the beginning of this command**. This will make available the *lessc* compiler for us so that we can compile Less files.

* Next, go to the CSS folder on your machine and rename the *styles.css* file that you have there as *styles-old.css*. This is to save the CSS file that we have been using so far. We will be creating a new *styles.css* file by compiling the Less file.
* Next type the following at the command prompt to compile the Less file into a CSS file:

`lessc styles.less styles.css`

# **Scss**

### **Adding Scss Variables**

* Open the *conFusion* project in a text editor of your choice. In the css folder, create a file named styles.scss. We will add the Scss code into this file.
* Add the following Scss variables into the file:

```scss
$lt-gray: #ddd;
$background-dark: #512DA8;
$background-light: #9575CD;
$background-pale: #D1C4E9;

// Height variables
$carousel-item-height: 300px;
```

We have just added a few color and a height variable. We will make use of these variables while defining the classes.

### **Scss Mixins**

* Next we add a mixin into the file as follows:

```scss
@mixin zero-margin($pad-up-dn, $pad-left-right) {
	margin:0px auto;
	padding: $pad-up-dn $pad-left-right;
}
```
We will make use of this to define several row classes next.

* Using the variables and Mixin class that we defined earlier, add the following row classes to the file:

```scss
.row-header{
    @include zero-margin(0px,0px);
}

.row-content {
    @include zero-margin(50px,0px);
    border-bottom: 1px ridge;
    min-height:400px;
}

.footer{
    background-color: $background-pale;
    @include zero-margin(20px, 0px);
}
.jumbotron {
    @include zero-margin(70px,30px);
    background: $background-light ;
    color:floralwhite;
}

address{
    font-size:80%;
    margin:0px;
    color:#0f0f0f;
}

body{
    padding:50px 0px 0px 0px;
    z-index:0;
}

.navbar-inverse {
    background-color: $background-dark;
}
.tab-content {
    border-left: 1px solid $lt-gray;
    border-right: 1px solid $lt-gray;
    border-bottom: 1px solid $lt-gray;
    padding: 10px;
}
```

Note the use of the variables and the mixin with various parameters in defining the classes.

### **Nesting Selectors**

* Next we add a carousel class to illustrate the use of nesting of classes in Scss, as follows:

```scss
.carousel {
    background:$background-dark;

    .carousel-item {
        height: $carousel-item-height;
        img {
            position: absolute;
            top: 0;n
            left: 0;
            min-height: 300px;
        }
    }
}
#carousel-button {
    right:0px;
    position: absolute;
    bottom: 0px;
}
```

### **Installing and using the node-sass module**

* Now we install the node module to support the compilation of the Scss file to a CSS file. To do this, type the following at the command prompt:

`npm install --save-dev node-sass`

This will install the *node-sass* NPM module into your project and also add it as a development dependency in your package.json file.

* Next open your package.json file and add the following line into the scripts object there. This adds a script to enable the compilation of the Scss file into a CSS file:

`"scss": "node-sass -o css/ css/"`

* In order to transform the Scss file to a CSS file, type the following at the prompt:

`npm run scss`

# **NPM Scripts** 

### **Watching for Changes and Parallelshell**

* First, we install two NPM packages *onchange* and *parallelshell* as follows:

`npm install --save-dev onchange parallelshell`

* Then, add the following two script items to *package.json*:

```js
"watch:scss": "onchange 'css/*.scss' -- npm run scss",
"watch:all": "parallelshell 'npm run watch:scss' 'npm run lite'"
```

* You will also update the start script as follows:

`"start": "npm run watch:all",`

* Then, type the following at the prompt to start watching for changes to the SCSS file, compile it to CSS, and run the server:

`npm start`

* Now, whenever you make any changes to styles.scss file, it will automatically be compiled to the corresponding css file.

### **Cleaning up a Distribution Folder** 

* Install the *rimraf* npm module by typing the following at the prompt:

`npm install --save-dev rimraf`

* Then, set up the following script?

`clean": "rimraf dist",`

### **Copying Fonts**

* Your project uses font-awesome fonts. These need to be copied to the distribution folder. To help us do this, install the *copyfiles* NPM module globally as follows:

`npm -g install copyfiles`

Remember to use *sudo* on mac and Linux.

* Then set up the following script:

`"copyfonts": "copyfiles -f node_modules/font-awesome/fonts/* dist/fonts",`

### **Compressing and Minifying Images**

* We use the *imagemin-cli* NPM module to help us to compress our images to reduce the size of the images being used in our project. Install the *imagemin-cli* module as follows:

`npm -g install imagemin-cli`

Remember to use *sudo* on mac and Linux. Some students have encountered issues with imagemin-cli not installing its plugins due to issues with global permissions on Mac. In that case try

`sudo npm install -g imagemin-cli --unsafe-perm=true --allow-root`

* Then set up the following script:

` "imagemin": "imagemin img/* -o dist/img",`

### **Preparing the Distribution Folder**

* Open *.gitignore* and update it as follows. We do not want the dist folder to be checked into the git repository.

```
node_modules
dist
```

* Then, install the *usemin-cli*, *cssmin*, *uglifyjs* and *htmlmin* NPM packages as follows:

`npm install --save-dev usemin-cli cssmin uglifyjs htmlmin`

* Add the following two scripts to the package.json file:

```json
"usemin": "usemin contactus.html -d dist --htmlmin -o dist/contactus.html && usemin aboutus.html -d dist --htmlmin -o dist/aboutus.html &&  usemin index.html -d dist --htmlmin -o dist/index.html",
"build": "npm run clean && npm run imagemin && npm run copyfonts && npm run usemin"
```

* Open index.html and surround the css links inclusion code as follows:

```html
<!-- build:css css/main.css -->
<link rel="stylesheet" href="node_modules/bootstrap/dist/css/bootstrap.min.css">
<link rel="stylesheet" href="node_modules/font-awesome/css/font-awesome.min.css">
<link rel="stylesheet" href="css/bootstrap-social.css">
<link href="css/styles.css" rel="stylesheet">
<!-- endbuild -->
```
* Do the same change in *aboutus.html* and *contactus.html*
* Similarly, open *index.html* and surround the js script inclusion code as follows:

```html
<!-- build:js js/main.js -->
<script src="node_modules/jquery/dist/jquery.min.js"></script>
<script src="node_modules/tether/dist/js/tether.min.js"></script>
<script src="node_modules/bootstrap/dist/js/bootstrap.min.js"></script>
<script src="js/scripts.js"></script>
<!-- endbuild --> 
```
* Do the same change in *aboutus.html* and *contactus.html*
* To build the distribution folder, you can type the following at the prompt:
`npm run build`

* This will build the dist folder containing the files that are a self-contained version of your project. You can now copy the contents of this folder to a web server that hosts your website.

# **Grunt**

### **Installing Grunt**

* At the command prompt, type the following to install Grunt command-line interface (CLI):

`npm install -g grunt-cli`

This will install the Grunt CLI globally so that you can use them in all projects.

* Next install Grunt to use within your project. To do this, go to the *conFusion* folder and type the following at the prompt:

`npm install grunt --save-dev`

This will install local per-project Grunt to use within your project.

### **Creating a Grunt File**

* Next you need to create a Grunt file containing the configuration for all the tasks to be run when you use Grunt. To do this, create a file named *Gruntfile.js* in the *conFusion* folder.
* Next, add the following code to Gruntfile.js to set up the file to configure Grunt tasks:

```js
'use strict';

module.exports = function (grunt) {
    // Define the configuration for all the tasks
    grunt.initConfig({

    });
}; 
```
This sets up the Grunt module ready for including the grunt tasks inside the function above.

### **Compiling SCSS to CSS**

* Next, we are going to set up our first Grunt task. The SASS task converts the SCSS code to CSS. To do this, you need to include some Grunt modules that help us with the tasks. Install the following modules by typing the following at the prompt:

```
npm install grunt-sass --save-dev
npm install time-grunt --save-dev
npm install jit-grunt --save-dev
```

The first one installs the Grunt module for SCSS to CSS conversion. The time-grunt module generates time statistics about how much time each task consumes, and jit-grunt enables us to include the necessary downloaded Grunt modules when needed for the tasks.

* Now, configure the SASS task in the Gruntfile as follows, by including the code inside the function in *Gruntfile.js*:

```js
'use strict';

module.exports = function (grunt) {
    // Time how long tasks take. Can help when optimizing build times
    require('time-grunt')(grunt);

    // Automatically load required Grunt tasks
    require('jit-grunt')(grunt);

    // Define the configuration for all the tasks
    grunt.initConfig({
        sass: {
            dist: {
                files: {
                    'css/styles.css': 'css/styles.scss'
                }
            }
        }
    });

    grunt.registerTask('css', ['sass']);
};
```
* Now you can run the grunt SASS task by typing the following at the prompt:

`grunt css`

### **Watch and Serve Tasks**

* The final step is to use the Grunt modules watch and browser-sync to spin up a web server and keep a watch on the files and automatically reload the browser when any of the watched files are updated. To do this, install the following grunt modules:

```
npm install grunt-contrib-watch --save-dev
npm install grunt-browser-sync --save-dev
```
* After this, we will configure the browser-sync and watch tasks by adding the following code to the Grunt file:

```js
watch: {
    files: 'css/*.scss',
    tasks: ['sass']
},
browserSync: {
    dev: {
        bsFiles: {
            src : [
                'css/*.css',
                '*.html',
                'js/*.js'
            ]
        },
        options: {
            watchTask: true,
            server: {
                baseDir: "./"
            }
        }
    }
}
```

* Then add the following task to the Grunt file:

`grunt.registerTask('default', ['browserSync', 'watch']);`

* Now if you type the following at the command prompt, it will start the server, and open the web page in your default browser. It will also keep a watch on the files in the css folder, and if you update any of them, it will compile the scss file into css file and load the updated page into the browser (livereload)

`grunt`

### **Copying the Files and Cleaning Up the Dist Folder**

* Next you will install the Grunt modules to copy over files to a distribution folder named dist, and clean up the dist folder when needed. To do this, install the following Grunt modules:

```
npm install grunt-contrib-copy --save-dev
npm install grunt-contrib-clean --save-dev
```

* You will now add the code to perform the copying of files to the dist folder, and cleaning up the dist folder. To do this, add the following code to *Gruntfile.js*. This should be added right after the configuration of the SASS task.:

```js
copy: {
    html: {
        files: [
        {
            //for html
            expand: true,
            dot: true,
            cwd: './',
            src: ['*.html'],
            dest: 'dist'
        }]
    },
    fonts: {
        files: [
        {
            //for font-awesome
            expand: true,
            dot: true,
            cwd: 'node_modules/font-awesome',
            src: ['fonts/*.*'],
            dest: 'dist'
        }]
    }
},

clean: {
    build: {
        src: [ 'dist/']
    }
}
```

* Remember to add the comma after the end of the SASS task.

### **Compressing and Minifying Image**

* Next we install the grunt-contrib-imagemin module and use it to process the images. To install this module type at the prompt:

`npm install grunt-contrib-imagemin --save-dev`

* Then, configure the imagemin task as shown below in the Gruntfile:

```js
imagemin: {
    dynamic: {
        files: [{
            expand: true,                  // Enable dynamic expansion
            cwd: './',                   // Src matches are relative to this path
            src: ['img/*.{png,jpg,gif}'],   // Actual patterns to match
             dest: 'dist/'                  // Destination path prefix
        }]
    }
}
```

### **Preparing the Distribution Folder and Files**

We are now going to use the Grunt *usemin* module together with concat, *cssmin*, *uglify* and *filerev* to prepare the distribution folder. To do this, install the following Grunt modules:

```
npm install grunt-contrib-concat --save-dev
npm install grunt-contrib-cssmin --save-dev
npm install grunt-contrib-uglify --save-dev
npm install grunt-filerev --save-dev
npm install grunt-usemin --save-dev
```

* Add the following line to the scripts block in *aboutus.html* and *contactus.htm*

```js
 <script src="js/scripts.js"></script>
```

* Next, update the task configuration within the Gruntfile.js with the following additional code to introduce the new tasks:

```js
useminPrepare: {
    foo: {
        dest: 'dist',
        src: ['contactus.html', 'aboutus.html', 'index.html']
    },
    options: {
        flow: {
            steps: {
                css: ['cssmin'],
                js: ['uglify']
            },
            post: {
                css: [{
                    name: 'cssmin',
                    createConfig: function(context, block){
                        var generated = context.options.generated;
                        generated.options = {
                            keepSpecialComments: 0, rebase: false
                        };
                    }
                }]
            }
        }
    }
},
// Concat
concat: {
    options: {
        separator: ';'
    },
    // dist configuration is provided by useminPrepare
    dist: {}
},
// Uglify
uglify: {
    // dist configuration is provided by userminPreapare
    dist: {}
},
cssmin: {
    dist: {}
},
//Filerev
filerev: {
    options: {
        encoding: 'utf8',
        algorithm: 'md5',
        length: 20
    },
    release: {
        // filerev: release hashes(md5) all assets (images, js and css)
        // in dist directory
        files: [{
            src: [
                'dist/js/*.js',
                'dist/css/*.css',
            ]
        }]
    }
},
// Usemin
// Replace all assets with their revved version in html and css files.
// options.assetDirs contains the directories for finding assets
// according to their relative paths
usemin: {
    html: ['dist/contactus.html', 'dist/abouts.html', 'dist/index.html'],
    options : {
    assetsDirs: ['dist', 'dist/css', 'dist/js']
    }
},
```

* Next, update the jit-grunt configuration as follows, to inform it that useminPrepare task depends on the usemin package:

```js
require('jit-grunt')(grunt, {
    useminPrepare: 'grunt-usemin'
});
```

* Next, update the Grunt build task as follows:

```js
grunt.registerTask('build', [
    'clean',
    'copy',
    'imagemin',
    'useminPrepare',
    'concat',
    'cssmin',
    'uglify',
    'filerev',
    'usemin'
]);
```

* Now if you run Grunt, it will create a dist folder with the files structured correctly to be distributed to a server to host your website. To do this, type the following at the prompt:

`grunt build`

# **Gulp**

### **Installing Gulp**

* At the command prompt, type the following to install Gulp command-line interface (CLI) globally:

`npm install -g gulp-cli`

This will install the Gulp globally so that you can use it in all projects.

* Next install Gulp to use within your project. To do this, go to the *conFusion* folder and type the following at the prompt:

`npm install gulp --save-dev`

This will install local per-project Gulp to use within your project.

### **Install Gulp Plugins for SASS and Browser-Sync**

* Install all the Gulp plugins that you will need for this exercise. To do this, type the following at the command prompt:

`npm install gulp-sass  browser-sync --save-dev`

### **Creating a Gulp File**

* Next you need to create a Gulp file containing the tasks to be run when you use Gulp. To do this, create a file named *gulpfile.js* in the *conFusion* folder.

### **Loading Gulp Plugins**

* Load in all the Gulp plugins by including the following code in the Gulp file:

```js
'use strict';

var gulp = require('gulp'),
    sass = require('gulp-sass'),
    browserSync = require('browser-sync');
```

### **Adding Gulp Tasks for SASS and Browser-Sync**

* Next, we will add the code for the SASS task, the Browser-Sync task and the default task as follows:

```js
 
gulp.task('sass', function () {
  return gulp.src('./css/*.scss')
    .pipe(sass().on('error', sass.logError))
    .pipe(gulp.dest('./css'));
});

gulp.task('sass:watch', function () {
  gulp.watch('./css/*.scss', ['sass']);
});

gulp.task('browser-sync', function () {
   var files = [
      './*.html',
      './css/*.css',
      './img/*.{png,jpg,gif}',
      './js/*.js'
   ];

   browserSync.init(files, {
      server: {
         baseDir: "./"
      }
   });

});

// Default task
gulp.task('default', ['browser-sync'], function() {
    gulp.start('sass:watch');
});
```

* Save the Gulp file

### **Running the Gulp Tasks**

* At the command prompt, if you type gulp it will run the default task:

`gulp`

## **Copying the Files and Cleaning up the Dist Folder**

* We will now create the tasks for copying the font files and cleaning up the distribution folder. To do this we will first install the *del* Node module and require it in the Gulp file as follows:

`npm install del --save-dev`

```js
var ...
    del = require('del'),
    ...
```

* Next, we will add the code for the Clean task and the copyfonts task as follows:

```js
// Clean
gulp.task('clean', function() {
    return del(['dist']);
});

gulp.task('copyfonts', function() {
   gulp.src('./node_modules/font-awesome/fonts/**/*.{ttf,woff,eof,svg}*')
   .pipe(gulp.dest('./dist/fonts'));
});
```

### **Compressing and Minifying Images**

* We will now install the gulp-imagemin plugin and configure the imagemin task. To do this we install the plugin and require it as follows:

`npm install gulp-imagemin --save-dev`

```js
var ...
    imagemin = require('gulp-imagemin'),
    ...
```

* Next, we create the *imagemin* task as follows:

```js
// Images
gulp.task('imagemin', function() {
  return gulp.src('img/*.{png,jpg,gif}')
    .pipe(imagemin({ optimizationLevel: 3, progressive: true, interlaced: true }))
    .pipe(gulp.dest('dist/img'));
});
```

### **Preparing the Distribution Folder and Files**

* We now install the gulp-usemin and other related Gulp plugins and require them as follows:

`npm install gulp-uglify gulp-usemin gulp-rev gulp-clean-css gulp-flatmap gulp-htmlmin --save-dev`

```js
var ...
    uglify = require('gulp-uglify'),
    usemin = require('gulp-usemin'),
    rev = require('gulp-rev'),
    cleanCss = require('gulp-clean-css'),
    flatmap = require('gulp-flatmap'),
    htmlmin = require('gulp-htmlmin');
```

* We configure the usemin and the build task as follows:

```js
gulp.task('usemin', function() {
  return gulp.src('./*.html')
  .pipe(flatmap(function(stream, file){
      return stream
        .pipe(usemin({
            css: [ rev() ],
            html: [ function() { return htmlmin({ collapseWhitespace: true })} ],
            js: [ uglify(), rev() ],
            inlinejs: [ uglify() ],
            inlinecss: [ cleanCss(), 'concat' ]
        }))
    }))
    .pipe(gulp.dest('dist/'));
});

gulp.task('build',['clean'], function() {
    gulp.start('copyfonts','imagemin','usemin');
});
```

* Save the Gulp file

### **Running the Gulp Tasks**

* At the command prompt, if you type *gulp build* it will run the build task:

`gulp build`