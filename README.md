<<<<<<< HEAD
# [Start Bootstrap - Clean Blog Jekyll](https://startbootstrap.com/themes/clean-blog-jekyll/) - Official Jekyll Version

[Clean Blog Jekyll](https://startbootstrap.com/themes/clean-blog-jekyll/) is a stylish, responsive blog theme for [Bootstrap](https://getbootstrap.com/) created by [Start Bootstrap](https://startbootstrap.com/). This theme features a blog homepage, about page, contact page, and an example post page along with a working contact form powered by [Formspree](https://formspree.io/).

This repository holds the official Jekyll version of the Clean Blog theme on Start Bootstrap!

## Preview

[![Clean Blog (Jekyll) Preview](https://startbootstrap.com/assets/img/screenshots/themes/clean-blog-jekyll.png)](http://StartBootstrap.github.io/startbootstrap-clean-blog-jekyll/)

**[View Live Preview](http://StartBootstrap.github.io/startbootstrap-clean-blog-jekyll/)**

## Installation & Setup

### Using RubyGems

When installing the theme using RubyGems, demo images, posts, and pages are not included. Follow the instructions below for complete setup.

1. (Optional) Create a new Jekyll site: `jekyll new my-site`
2. Replace the current theme in your `Gemfile` with `gem "jekyll-theme-clean-blog"`.
3. Install the theme (run the command inside your site directory): `bundle install`
4. Replace the current theme in your `_config.yml` file with `theme: jekyll-theme-clean-blog`.
5. Build your site: `bundle exec jekyll serve`

Assuming there are no errors and the site is building properly, follow these steps next:

1. Create the following pages if they do not exist already (or change the extension of existing markdown files from `.md` to `.html`):

   * `index.html` - set to `layout: home`
   * `about.html` - set to `layout: page`
   * `contact.html` - set to `layout: page`
   * `posts/index.html` - set to `layout: page` (you will also need to create a `posts` directory)

2. Configure the `index.html` front matter. Example:

    ```markdown
    ---
    layout: home
    background: '/PATH_TO_IMAGE'
    ---
    ```

3. Configure the `about.html`, `contact.html`, and `posts/index.html` front matter. Example:

    ```markdown
    ---
    layout: page
    title: Page Title
    description: This is the page description.
    background: '/PATH_TO_IMAGE'
    ---
    ```

4. For each post in the `_posts` directory, update the front matter. Example:

    ```markdown
    ---
    layout: post
    title: "Post Title"
    subtitle: "This is the post subtitle."
    date: YYYY-MM-DD HH:MM:SS
    background: '/PATH_TO_IMAGE'
    ---
    ```

    For reference, look at the [demo repository](https://github.com/StartBootstrap/startbootstrap-clean-blog-jekyll) to see how the files are set up.

5. Add the form to the `contact.html` page. Add the following code to your `contact.html` page:

    ```html
    <form name="sentMessage" id="contactForm" novalidate>
      <div class="control-group">
        <div class="form-group floating-label-form-group controls">
          <label>Name</label>
          <input type="text" class="form-control" placeholder="Name" id="name" required data-validation-required-message="Please enter your name.">
          <p class="help-block text-danger"></p>
        </div>
      </div>
      <div class="control-group">
        <div class="form-group floating-label-form-group controls">
          <label>Email Address</label>
          <input type="email" class="form-control" placeholder="Email Address" id="email" required data-validation-required-message="Please enter your email address.">
          <p class="help-block text-danger"></p>
        </div>
      </div>
      <div class="control-group">
        <div class="form-group col-xs-12 floating-label-form-group controls">
          <label>Phone Number</label>
          <input type="tel" class="form-control" placeholder="Phone Number" id="phone" required data-validation-required-message="Please enter your phone number.">
          <p class="help-block text-danger"></p>
        </div>
      </div>
      <div class="control-group">
        <div class="form-group floating-label-form-group controls">
          <label>Message</label>
          <textarea rows="5" class="form-control" placeholder="Message" id="message" required data-validation-required-message="Please enter a message."></textarea>
          <p class="help-block text-danger"></p>
        </div>
      </div>
      <br>
      <div id="success"></div>
      <div class="form-group">
        <button type="submit" class="btn btn-primary" id="sendMessageButton">Send</button>
      </div>
    </form>
    ```

    Make sure you have the `email` setting in your `_config.yml` file set to a working email address! Once this is set, fill out the form and then check your email, verify the email address using the link sent to you by Formspree, and then the form will be working!

6. Build your site: `bundle exec jekyll serve`

### Using Core Files

When using the core files, the demo images, posts, and pages are all included with the download. After following the instructions below, you can then go and change the content of the pages and posts.

1. [Download](https://github.com/StartBootstrap/startbootstrap-clean-blog-jekyll/archive/master.zip) or Clone the repository.
2. Update the following configuration settings in your `_config.yml` file:

    * `baseurl`
    * `url`
    * `title`
    * `email` (after setting this setting to a working email address, fill out the form on the contact page and send it - then check your email and verify the address and the form will send you messages when used)
    * `description`
    * `author`
    * `twitter_username` (Optional)
    * `facebook_username` (Optional)
    * `github_username` (Optional)
    * `linkedin_username` (Optional)
    * `instagram_username` (Optional)

3. Build your site: `bundle exec jekyll serve`

## Bugs and Issues

Have a bug or an issue with this template? [Open a new issue](https://github.com/StartBootstrap/startbootstrap-clean-blog-jekyll/issues) here on GitHub!

## About

Start Bootstrap is an open source library of free Bootstrap templates and themes. All of the free templates and themes on Start Bootstrap are released under the MIT license, which means you can use them for any purpose, even for commercial projects.

* <https://startbootstrap.com>
* <https://twitter.com/SBootstrap>

Start Bootstrap was created by and is maintained by **[David Miller](http://davidmiller.io/)**.

* <http://davidmiller.io>
* <https://twitter.com/davidmillerhere>
* <https://github.com/davidtmiller>

Start Bootstrap is based on the [Bootstrap](https://getbootstrap.com/) framework created by [Mark Otto](https://twitter.com/mdo) and [Jacob Thorton](https://twitter.com/fat).

## Copyright and License

Copyright 2013-2021 Start Bootstrap LLC. Code released under the [MIT](https://github.com/StartBootstrap/startbootstrap-clean-blog-jekyll/blob/master/LICENSE) license.
=======
# BlogBox
BlogBox is a minimal, bold, responsive, and easy-to-use Jekyll theme. It’s a perfect fit for artists, photographers, or creative bloggers looking for a bold design theme.

[Live Demo](https://blogbox.netlify.app/)

## Preview

[![Blogbox preview](/blogbox_preview.jpeg "Blogbox preview")](https://blogbox.netlify.app/)

## Theme features

+ Responsive layout – your blog will be accessible on various devices (iPhone, iPad, Android, etc.)
+ Clean, well commented code, easy to customize
+ Optional fixed navigation
+ Author information
+ Tag page support
+ Code syntax highlighter
+ Newsletter, latest posts and tag cloud widgets
+ Sharing post integration
+ Social media icons

## Local Installation
> How to install and use the theme

_Note: this theme cannot be installed as a gem in your Gemfile and config, therefore the only way to use this theme is to clone the entire repo and put your content in it among the styling._

Install Jekyll as per [Jekyll docs](https://jekyllrb.com/docs/).

Clone the repo or your fork.

Navigate to the repo.

Install the dependencies:

```sh
$ bundle config set --local path vendor/bundle
$ bundle install
```

Start a dev server, with verbose error traces:

```sh
$ bundle exec jekyll serve --trace
```

## Development
> How to set up and run the theme as a standalone site locally

Follow the steps in the section above.

## Deployment

Please see the [Deployment Methods](https://jekyllrb.com/docs/deployment-methods/) page on the Jekyll website.

### Manual Deployment

Jekyll outputs your static site to the `_site`. directory by default. You can transfer the contents of this directory to almost any hosting provider to get your site live. This can be tedious, so some automated deploy approaches are listed below.

### Netlify

This theme is prepared to be hosted on [Netlify](https://www.netlify.com/). All you need to do is create a new public or private repository on GitHub or GitLab. Upload the theme to the repository and link your repo to Netlify. Please check this [blog post](https://www.netlify.com/blog/2015/10/28/a-step-by-step-guide-jekyll-3.0-on-netlify/#step-2-link-to-your-github) for step-by-step guidelines.

### Amazon S3

If you want to host your site on Amazon S3, you can do so by using the [s3_website application](https://github.com/laurilehmijoki/s3_website). It will push your site to Amazon S3, where it can be served like any web server, dynamically scaling to almost unlimited traffic. Well, S3 itself is not built for speed so you probably want to put some CDN like CloudFront on top of your S3 objects.

### GitHub Pages

See the [GitHub Actions](https://jekyllrb.com/docs/continuous-integration/github-actions/) deploy guide on Jekyll docs to build with GitHub Actions and host with GitHub Pages.

## License

Licensed under [MIT](/LICENSE).
>>>>>>> 2718f83 (new)
