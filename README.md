## jekyll-angular

Boilerplate project to enable quick development of a static website

### Setting up the project

This project assumes working knowledge of both [Jekyll](http://jekyllrb.com) and [AngularJS](https://angularjs.org).

#### Highly recommended

- Change the project name in package.json and bower.json to match the name of your project.
- Then rename the files ./less/jekyll-angular.less and ./javascript/src/jekyll-angular.js to match the name of your project.
- Finally in the index.html find the css and script imports and rename these to match too.

### Making changes

The project is setup with three main folders;

`javascript`
`less`
and `site`

#### Javascript

In here you can build up any javascript you need to support dynamic interactions on your site, these files will be compiled automatically for you on deployment / preview, as we are looking to support AngularJS a basic setup using Angular for all javascript is used.

#### LESS

The less files give the ability to personalise the design of your site or extend any CSS frameworks you might wish to use.

#### Site

In here are all the HTML files you can also use markdown should you wish as per a normal jekyll website.

### Building the project

First you need to install the supporting libraries, we use node for this you can [install node via their website](https://nodejs.org), with node installed you can now install grunt using the command `npm install -g grunt-cli`

With these tools now installed you can install the project dependencies using the command `npm install`

- During development use `grunt run` on the command line which will monitor changes and update the site for you. You can then use 'http://localhost:1337' and changes made will auto-reload thanks to livereload.

- To create the static site with minified assets use the command `grunt build`

### Deploying your site

All static site assets are automatically generated into a `_gh_pages` folder, this is the folder you can deploy onto your web server, or can use with [GitHub pages](https://pages.github.com).

If you are using AWS S3 and have the aws-cli installed you can also use the command `aws s3 sync . s3://bucket --acl=public-read --exclude "*.DS_Store" --delete` where s3://bucket is the name of your existing bucket on S3, don't forget to always simulate a deployment first you can add the `--dryrun` flag on the end of the command to do this.
