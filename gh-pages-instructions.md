## Github Pages Setup Instructions


Find a demo of the finished product [here](https://jimmyankles.github.io).

### Successfully install Jekyll

`gem install jekyll`

##### Installing Xcode Command-Line Tools
> If you run into issues installing Jekyll's dependencies which make use of native extensions and are using macOS, you will need to install Xcode and the Command-Line Tools it ships with. Download them in Preferences → Downloads → Components.


### Create a repo to host your blog

1. Create a public repository (+ in top-right corner) named `{Github Username}.github.io`
    1. Initialise the repository with a README.md and a `Jekyll .gitignore`. The contents of your README.md will be what shows up on the homepage of your site initially.
    2. Clone the repository to somewhere sensible on your computer `git clone {Repository SSH or HTTPS address}
2. Go into the cloned repository directory. `cd {Github Username}.github.io`
3. Create an `index.html` file in there to test. `echo “Hello World” > index.html
    1. Commit and push this new file
        1. `git add -A` (`-A` means “all)
        2. `git commit -m “Initial Commit”` (`-m` allows you to specify a commit message quickly)
        3. `git push -u origin master`
4. TIME TO TEST THAT
    1. Go into a browser and navigate to `http://{Github Username}.github.io`
    2. You should see what you wrote in your README.md rendered on the webpage. 

### JEKYLL TIME

For the purposes of this workshop we will be using the [Krishna](https://github.com/sharu725/krishna/tree/gh-pages) Jekyll theme. We are going to completely overwrite the currently `master` branch with this repo’s `master`, and use it as a base. 

1. Set-up Krishna as the `upstream` remote. Use either HTTP or SSH
    1. `git remote add upstream git@github.com:sharu725/krishna.git`
    2. `git remote add upstream https://github.com/sharu725/krishna.git`
2. `git fetch upstream`
3. Overwrite your `master` branch: `git reset —hard upstream/master`
4. Overwrite your `master` branch on Github: `git push —force-with-lease`

### Customizing the base theme

First, and most importantly, we have to change the `config.yml` file.

1. Change the `title:` variable to your name.
2. Change the `baseurl:` to `””`

#### Time to Test

Navigate to `http://{Github Username}.github.io` and check that the site rendered according to the base theme.

#### Further customisation

1. Change the footer to:  `Find my Github at <a href="https://github.com/{username}”>github.com/{username}</a>`
2. Change the theme colour in `css/main.scss` (this might not update properly until you update a `.md` file
3. Remove this line from `default.html`:   `<a href="https://github.com/sharu725/krishna"><i class="fa fa-code-fork"></i>&nbsp;Project</a>`

#### Editing the About page

Static pages are created in the `_pages` folder, and written in Markdown with Jeykll ‘front-matter’. We’ll edit the *About* page so it actually includes info about yourself!

Open `about.md` in an editor and put stuff in about yourself. Heres a template: 

```
---
layout: post
title: About Me
permalink: /about/
---

My name is YOUR NAME and I'm currently completing a Computer Science/IT/Software Engineering degree at [RMIT University](http://www.rmit.edu.au/) in [Melbourne](https://en.wikipedia.org/wiki/Melbourne). I'm in my XXXXX year and will be completing my studies in 201X. 

You can find my [Github Profile here](https://github.com/thundergolfer) and my [LinkedIn Profile here](https://www.linkedin.com/in/jonathonbelotti/).

**My Current Project is: PROJECT NAME**

This is a project description it has stuff in it about what tech your project uses, what problems it solves, blah, blah, blah. Here is a short second sentence. That's about all we need.

<a class="github-button" href="https://github.com/thundergolfer/the-general-problem-solver" data-style="mega" data-count-href="/thundergolfer/the-general-problem-solver" data-count-api="/repos/thundergolfer/the-general-problem-solver#stargazers_count" data-count-aria-label="# stargazers on GitHub" aria-label="Star PROJECT NAME on GitHub">Star</a>
<script async defer src="https://buttons.github.io/buttons.js"></script>

My main interests are in INTEREST_ONE, INTEREST_TWO, and INTEREST_THREE.
```

#### Editing the Contact Page

Update the `contact.md` page in `_pages`. Here’s a starting point:

```
---
layout: post
title: Contact
permalink: /contact/
---

These are my contact details.

**Email:** your_email@email.com
**Phone:** your number
**LinkedIn:** your LinkedIn
```
 
#### Cleaning out `_posts`

`_posts` is where your blog posts live. They are written in Markdown which is super simple. Delete all the posts in this folder except for one. We’ll use the last one as a template to create your first blog post.

#### Making your first post

Create a file named `2017-04-05-my-first-post.md` in `_posts`. Use the only remaining post in `_posts` as a base template. It is important to have the *front matter* section in your Markdown. It looks like this:

```
---
layout: post
title:  "Use it for free!"
categories: jekyll update
icon: motorcycle
---
```

The sections of it are pretty self explanatory. Available icons can be found at [http://fontawesome.io/icons/](http://fontawesome.io/icons/).

Then go ahead an type out anything as a first post using Markdown syntax, [here’s a guide.](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet)


### And You're Done!

Of course there's a lot more you can do to make this site your own, but for now it's great that you've got all this setup.
