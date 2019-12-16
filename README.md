# Drupal 8 Starter Theme for CUL

Written as a sub-theme of Drupal Bootstrap. Install the latest version of the [Bootstrap theme for Drupal](https://www.drupal.org/project/bootstrap) to use and customize this theme.

At this time, no styling customizations have been applied. As the UX team refines and standardizes visual design for unit sites, some default styling overrides may appear - for now, all visual styling is Bootstrap default and ready to be customized.

## First Steps

*Theme Name Choice*
You must use a machine-readable (lowercase letters and underscores only) name for your theme! The theme name becomes a part of block names, and you may not be able to move them around.

Search and replace "d8starter" with your themename in themename.info.yml, themename.theme, themename.libraries.yml, config/schema/themename.schema.yml and config/install/themename.settings.yml. including renaming the files. The theme name must be replaced with the directory name of your new theme. Also rename the root folder to your theme name.

*Important Note!!*
If you do not change the file names and themename mentions within /config/schema and /config/install before setting your theme as the default, you may become unable to change the theme later. This can cause the site to fail to render at all, so be sure and get every themename mention in every file before enabling the theme.

## Helpful Inclusions

FontAwesome, Montserrat 400 and 700, and Source Sans Pro 300, 400 and 500 have been included via themename.libraries.yml

Cornell favicon (to override Bootstrap favicon)

Basic SVG logo for standard top red Cornell header (see How To section below for notes on making better browser-agnostic SVGs from Illustrator)

*To make the standard-ish red CU header - enable a block with catalog and hours links in the header region wrapped in a div with applied class "cu-banner" to apply these styles automatically.*

info.yml file is configured to load the theme's style.css stylesheet into CKeditor - this allows for better previews and to enable custom style dropdowns.

A few extra regions are included, and slightly rearranged from Bootstrap 3's defaults. Main page template is found in /templates/page.html.twig, using a .masthead div to wrap the header and navigation regions.

When adding menus to the Navigation and Navigation(collapsible) regions, the Main Menu is the one that has primary fancy features coded in via the class "navbar-nav" on the menu UL. Any menu that applies this class can enjoy these benefits; however, using the Main Menu is recommended.

The script found in utils.js is used by the fancy Search box function (code for the search box needs to be manually added in a custom block). If you are not using the dropdown-select search box, this can be removed.

## Suggested Block Configuration

For the standard-ish looking header, enable:

* CUL Header - you will need to make this block, by wrapping a piece of text or image in an element with an applied class of cu-banner. The class will apply the Cornell University logo, a red background, and your text will be right-aligned.
* Search - styled as per Math library
* Site branding - has a template that applies "Cornell University Library" to site title (unit library name or site name)
* Status messages (optional to have this in header)

## Sass Structure

style.css is compiled from style.scss, which uses the _default-variables, _overrides, and bootstrap component files.
You can put your theme-specific CSS into _overrides.scss, or you could put sitewide overrides into _overrides.scss and put specific element or feature CSS into _custom.scss, set up as a convenient location for knowing where your changes are.

## How To

Add a region: https://www.drupal.org/docs/8/theming-drupal-8/adding-regions-to-a-theme
Add a custom style sheet or js: https://www.drupal.org/docs/8/theming-drupal-8/adding-stylesheets-css-and-javascript-js-to-a-drupal-8-theme
Adding a template override, naming convention: https://drupal-bootstrap.org/api/bootstrap/docs%21Templates.md/group/templates/8

Make device- and browser-agnostic SVGs: Illustrator's default SVG generator outputs a header that looks somethign like this: <svg version="1.1" id="Layer_1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" x="0px" y="0px" width="188px" height="40px" viewBox="0 0 188 40" style="enable-background:new 0 0 188 40;" xml:space="preserve">

This works great until you try to view it on Windows machines with Explorer....and then the sizing is all wrong. To get consistent sizes across all browsers and devices, remove just the width and height properties and replace with preserveAspectRatio="xMidYMid meet". Then, set your image sizing in CSS if necessary.

## Last Steps

Take a screenshot and replace the default screenshot.png in the root directory of your theme.
Also remember to change the description in themename.info.yml!