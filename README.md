# personal-site
Build an HTML file
In the terminal, create an index.html file:

touch index.html 
Open this file in your text editor so we can add some basic HTML content. In the file, we'll start with the minimum — a DOCTYPE tag indicating HTML and an html tag containing head and body tags:

<!DOCTYPE html>
<html lang="en">
  <head>

  </head>
  <body>

  </body>
</html> 
Let's give this HTML a title tag and place it inside head:

<head>
  <title>My Website</title>
</head> 
Finally, we'll add a bit of starter content in the body:

<body>
  <h1>Hello World!</h1>
</body> 
Including some example text to start is important — when we publish the site, we'll be looking for this message to confirm everything worked. The completed file should look like this:

<!DOCTYPE html>
<html lang="en">
  <head>
    <title>My Website</title>
  </head>
  <body>
    <h1>Hello World!</h1>
  </body>
</html> 
Save the file. We now need to commit this file and push it to GitHub:

git add index.html
git commit -m "create basic HTML file"
git push 
Time to head back to GitHub!

Publish HTML as a GitHub Page
In your GitHub repository, click the Settings tab:

settings tab

Scroll through the settings until you find the GitHub Pages section:

settings

To enable GitHub Pages, first we need to set the Source to the default branch. Click the drop-down that says "None," then choose main.

select branch

Once set, click Save:

save button

The page will refresh. Along the top, a banner should appear that states the GitHub Page source was saved:

source saved

Scroll back to the GitHub Page settings. A new message will be present that includes a link to the newly published page:

site is ready to be published

Notice the URL isn't github.com/<your-username>, but instead, <your-username>.github.io.

Clicking on this link immediately may bring you to an error page. It can typically take up to ten minutes for the page to appear after being published, so wait a little bit and refresh. On refresh, you should see your HTML page rendered:

site published on GitHub

Woo-hoo!

Troubleshooting
In the event that it isn't a woo-hoo for you, here are a few troubleshooting options to try:

Double check the GitHub Page settings and make sure main is set as the source
If settings are correct, review the index.html file to make sure there are no typos or syntax errors
Create a new repository again, but hold off on creating an HTML file. Instead, only create a README.md file with some example text and use GitHub Pages to publish the repo. Once the Readme file is displaying as a GitHub Page, start going through the HTML file creation process again.
Continuing To Build
With an index.html file created, it is possible to add additional files to the site to incorporate CSS and JavaScript. One of the great things about GitHub Pages is that your published website will automatically update as you make changes to the repository files and push them to your remote. The process for updating becomes:

Create or modify a file
Add, commit, and push it to your remote
Wait a few minutes for GitHub to update your page
Visit your GitHub Page to see the newest changes
From here, you can choose to do whatever you like and customize your site as you please. However, we recommend adding and connecting two files now: a CSS file to style your HTML, and a JavaScript file to run code and manipulate the DOM.

Add and Connect a CSS File
In the terminal, create a CSS file alongside your index.html file

touch style.css 
Before we connect this file to our HTML, let's add a basic style rule to the file and save it so we'll know when the styling is working.

body {
  background: blue;
} 
Now, to connect this CSS file to our index.html, we need to modify the HTML head to include a link tag:

<head>
  <link rel="stylesheet" href="style.css">
  <title>My Website</title>
</head> 
The link tag is used to connect files to the HTML page. Note the tag has two atttributes. The first is rel, which specifies how the connected file relates to the HTML. In this case, we're indicating that we're relating a stylesheet.

The second attribute is href, which specifies the location of the file we're linking. Since we've put style.css right beside index.html in our repository, we can just provide the file name here.

Save the HTML file and open it locally. Your page should now be very blue.

Go ahead and add some better styling, then add, commit, and push the changes you've made. Remember, since you've added a style.css file and modified the index.html file, we'll need to add both files before committing:

git add style.css
git add index.html
git commit -m "add style.css, connect to index.html"
git push 
Add and Connect a JavaScript File
In the terminal, create a JS file alongside index.html.

touch script.js 
Let's add some basic code so we can see something once we've connected the JS file to our HTML file.

In script.js, let's create an h2 element and add some text content to it:

const h2 = document.createElement('h2');
h2.textContent = "This content added by JavaScript"; 
Now, we'll include code to add this h2 element to the body element in the DOM.

document.querySelector('body').appendChild(h2); 
Save this and switch over to index.html. To connect script.js to our HTML, we add a script tag inside body.

<script src="script.js"></script> 
This tag includes a src attribute. Like href from the link tag, src specifies the location of the script we want to run. Since script.js is side by side with index.html, we just write the file name.

After adding the script tag for JavaScript and the link tag for CSS, our HTML will look like this:

<!DOCTYPE html>
<html lang="en">
<head>
  <link rel="stylesheet" href="style.css">
  <title>My Website</title>
</head>
<body>
  <h1>Hello World!</h1>
  <script src="script.js"></script>
</body>
</html> 
Open the file locally. In addition to "Hello World!" being displayed, you should also see "This content added by JavaScript," confirming the code successfully ran.

Go ahead and add other JavaScript if you'd like, then add, commit, and push the changes you've made. Since you've added a script.js file and modified the index.html file, we'll need to add both files before committing:

git add script.js
git add index.html
git commit -m "add script.js, connect to index.html"
git push 
Remember when you push changes to GitHub, they will take a few moments to appear in GitHub Pages.

Conclusion
As it turns out, the technology we were already using to store our code is also useful for publishing websites. If you have any existing repositories that include HTML, you can now quickly turn your work there into shareable websites.

It makes sense if you consider GitHub is already storing your code. The work required to display the contents of an HTML file in your browser versus render that HTML file is similar.

As you continue your programming journey, you'll eventually start building parts of websites that can't be published using GitHub. Sites that require a server to store data, for instance, can't be published on GitHub Pages. GitHub is just rendering files it already has; it won't do more work than that. It turns out, that is actually quite a lot, though.

Many websites are made up of two pieces, a frontend and a backend. The frontend is what the client experiences, what renders in the browser, while the backend handles data storage and other work we don't want to burden the frontend with. GitHub Pages will work well as a host for most frontends, even those using modern frameworks like React. You'll soon see that frontends alone can actually be quite interesting and useful, even without a backend.

For simpler websites — personal sites, projects, etc... — GitHub pages is a great, free option for publishing content online.