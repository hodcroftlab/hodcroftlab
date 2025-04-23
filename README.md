# EVE Lab Website

Please see below for instructions on how to install, build, and modify the EVE website

- [Installation](#installation)
- [How to Edit Jekyll Sites](#how-to-edit-jekyll-sites)
- [Changing People Information](#changing-people-information)
- [To Do List](#to-do-list)

## Installation
### 🧪 EVE Lab Website: Local Setup Guide

This guide will help you set up the EVE Lab website on your own computer using [micromamba](https://mamba.readthedocs.io/en/latest/user_guide/micromamba.html). This will allow you to edit and preview the site locally before pushing changes. Please *always* preview changes before pushing!

### 🧰 Step 1: Create a Micromamba Environment

Open your terminal and create a new environment called `jekyll-lab` (or any name you like) and activate:

```bash
micromamba create -n jekyll-lab -c conda-forge ruby=3.4.1
micromamba activate jekyll-lab
```

### 📦 Step 2: Install Bundler & Dependencies

Install the version of `bundler` used in the project, and check it's installed correctly:

```bash
gem install bundler -v 2.6.2
bundler -v
```

Install necessary compilers:

```bash
micromamba install -c conda-forge gcc_linux-64 gxx_linux-64 pkg-config make libffi openssl
```

### 📂 Step 3: Clone the repository

Clone this repository to your local drive and enter it:

```bash
git clone git@github.com:hodcroftlab/hodcroftlab.git
cd hodcroftlab
```


### 📄 Step 4: Install Gems

Now install all the required Ruby gems (including Jekyll):

```bash
bundle _2.6.2_ install
```

### 🔧 Step 5: Serve the Website

```bash
jekyll serve
```

Some websites suggest to use `bundle exec jekyll serve` but this has never worked for Emma.

To view the site, navigate to [http://127.0.0.1:4000](http://127.0.0.1:4000) to view. Note you can only view the site locally while this is running. To stop running, use `CTRL+C`. To see changes, you have to stop & rebuild!

### (Bonus) 🔄️ Step 6: Build Before Pushing!

Remember, to actually change the website, you have to generate the new html files - so you **should always build before pushing to Github**, or you change won't show!

This is also a good reminder to always check your changes have worked the way you thought they should locally, before pushing!

If making small edits, as long as you've checked locally, it's ok to push directly to `master`. However if proposing larger changes, make them on a branch and submit a PR, so others can check it locally & ensure they like the change (and that it works as expected) before making changes to the website.


## How to Edit Jekyll Sites

### Static site building

Editing Jekyll sites takes some getting used to. The way they work is that base files are built and generate more 'recognizable' HTML files (and accompanying files) that are what are actually served as a website. These 'final' files are rebuilt every time you build the site, but stay the same between builds (hence why this is called a 'static' website - no information is generated 'only the fly').

In this site, the 'build' files are in the folder `docs` (the name of the original theme). **Never modify files in `docs` to try and make a change!** It will simply be overwritten the next time you build the site!

### How things are laid out

In general each page is made from a union of a few others pages. For example, our `index.html` simply pulls information from other pages - `intro.html`, `projects.html` and more (see the source of the page). Data is generally stored in a couple of places, then how that is formatted is stored elsewhere.

Some examples:

Information on people is generally in `_data/team.yml` and `_people/<name>.md`- these two are then pulled together to make everyone's individual page in `_layouts/person.html`. However, this data (at least the data from `team.yml`) is also used on `index.html` (via `_includes/team-preview.html`) and `_pages/about.html` to make the little rows of circle-faces.

Projects and collaborations are easier - the page format is in `_layouts/collaboration.html` and `_layouts/project.html` and the information is on individual pages in `_collaborations/` and `_projects/`. (The layout for displaying all of them together in the 'View All' pages is in `_pages/collaborations.html` and `_pages/projects.html`.) Note that we specify what kind of layout the project and collaboration pages should use in the header (ex: `layout: project`). 

### Ok, this seems complicated. How do I change something?

Luckily you shouldn't have to worry too much about layout changes (let Emma know if you think something could be improved - or at least ask her before attempting!).

Generally, you should focus on editing the `.md` files to add information. To see how to edit your own or others personal pages, see [changing people information](#changing-people-information).

To edit a project or a collaboration, just find the corresponding `.md` file in `_projects/` or `collaborations/`. To change their photos, add the image to `assets/images/projects` or `assets/images/collaborations` and modify the `image:` property in the `.md` file. (Please don't modify the logos without talking to Emma first.)

To *add* a project or collaboration, create a new `.md` file in the correct folder, following the format of existing files (don't forget an image, and for collaborations, a square, grayscale icon!). Then add a link in the menu at the top of the website by adding a new entry in `_data/nav.yml`. 

Ensure you add the name of anyone else involved in the project/collaboration, and check to see if you should add this project/collaboration to anyone's page! (Via their `_people/<name>.md` file.)


## Changing People information

There are two places to update information about a person:

`_data/team.yml` is the list of people who will appear on the About and Index (front) pages, and also includes: 
- Social media info (orcid, google scholar, bsky, linkedin, etc)
- Image on the About/Index page
- Description on the About/Index page (PhD student, etc)
- Interests that will appear on your main page

`_people/<name>.md` contains:
- Photo that will appear on your page
- Quote that will appear on the `/people` page (on mouseover)
- 'Role' for sorting on the `/people` page (ex: `member`, `alumni`)
- Projects you are involved in (appears on your page) (copy this exactly from `_data/nav.yml`!)
- Text that you write about yourself, as the main content

To change your photo, the easiest thing to do is to just replace the photo of yourself `assets/images/people` and ensure it's named the same! Ensure your photo is square (or it won't crop correctly) and isn't huge (will load slowly). Resize if you need!

To change your 'socials' (also ORCiD/GScholar) you can generally just add a new entry to your section of `_data/team.yml` - currently supported are Twitter, Github, Bluesky, ORCiD, Google Scholar (`gscholar`), and LinkedIn. Talk to Emma about adding any others!

## To Do list:

- Set real pictures for all projects
- Fix/adjust/find better pictures for all collaborations
- For both of the above, set picture size?
- Write pages for all projects
- Write pages for all collaborations
- Reformat blog pages
- Write at least 1 blog post
- Everyone fill in their own page
