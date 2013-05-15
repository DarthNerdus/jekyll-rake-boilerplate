# Jekyll Rake Boilerplate

*Jekyll Rake Boilerplate* is a small rake "boilerplate" for doing common tasks with the static site generator [Jekyll](http://jekyllrb.com/ "Jekyll"), such as generating your site, preview it in your default browser, creating a new post from a template, or publishing a post and checking it into your git repository.

Please note that the code is intentionally "messy" and quite un-DRY so that'll be easier to take the parts that you want and toss away the others.

## Usage

### Tasks

    rake draft    # Create a draft in _drafts [title, template, meta]
    rake preview  # Launch a preview of the site in the browser [drafts (true/false)]
    rake publish  # Move a post from _drafts to _posts

`rake draft title="Hello world"` creates a new post in the `_posts` directory by reading the default template file, adding the title you've specified and generating a filename by using the current date and the title. You may also specify an alternative template within your `_templates` folder and specify a `meta:` value for the YAML data of your post.

`rake publish post="hello-world"` moves a post from the `_drafts` directory to the `_posts` directory and appends the current date to it, as well as specifying the time of publishing within the YAML data of the post. If there's no post title in the task it'll instead list all of the posts in the `_drafts` directory. This task will also stash any changes within your repository, add and commit your post, and unstash your other changes.

`rake preview drafts="false"` launches your default browser and then generates and watches the site so you can preview it. Additionally, you may specify whether or not to include draft posts. Defaults to `true`. Please note that you may need to hit refresh once your browser has launched. This task requires the ruby gem [Launchy](http://rubygems.org/gems/launchy "Launchy"). You can install by typing `gem install launchy` or `sudo gem install launchy` in your terminal/command prompt.


### _config.yml

    post:
      template:
      extension:
    editor:

## Examples

### Post Template (Text)

    --- 
    layout: text
    title:
    date: 2016-01-01 <!-- This ensures the post is at the top while previewing -->
    ---

### Post Template (Link Post)

    --- 
    layout: link
    title: 
    meta: 
    date: 2016-01-01
    ---

### Editor

    editor: subl

## Credits

Huge thanks to [gummesson](https://github.com/gummesson "gummesson on GitHub") for creating this project.

Many thanks to [ixti](https://github.com/ixti "ixti on GitHub") for finding the `Launchy` gem and pointing me in the right direction.

## License

**The MIT License (MIT)**

*Copyright (c) 2012 Ellen Gummesson*

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
