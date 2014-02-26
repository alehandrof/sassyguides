# SassyGuides

SassyGuides is a framework for customizing [LibGuides](http://springshare.com/libguides/) written in [Sass](http://sass-lang.com/) by [Alex Armstrong](http://github.com/alehandrof/).

SassyGuides was written as a proof-of-concept for SpringyCamp 2013. Following the announcement of the second version of LibGuides soon after, it did not make sense to develop it further. SassyGuides has not been sufficiently tested to use in a production environment. In other words: it's full of bugs that I won't fix.

Will there be a new version for LibGuides v2? I don't know yet :)

- Check out the [live demo](http://sandbox.campusguides.com/sassyguides) to see what it looks like.
- Read the [changelog](http://github.com/alehandrof/sassyguides/blob/master/CHANGELOG.md) to find out what's changed recently.
- Questions or comments? Contact me by [email](mailto:alehandrof@gmail.com) or on [twitter](http://twitter.com/alehandrof).

---

## Quick Start

### 1. Get SassyGuides

- [Download the latest release](http://github.com/alehandrof/sassyguides/zipball/master)
- Clone the repository: `git clone git://github.com/alehandrof/sassyguides.git`.

### 2. Compile SassyGuides

- Use the recommended environment (see below) which uses a Ruby-powered combination of Guard, Compass & Livereload
- Use the [Compass](http://compass-style.org/install/) gem.
- Use a GUI app: (list not exhaustive)
    - [Compass.app](http://compass.handlino.com/). Linux, Mac & Windows. Commercial.
    - [CodeKit](http://incident57.com/codekit/). Mac. Commercial.
    - [LiveReload](http://livereload.com/). Mac & Windows. Commercial.
    - [Prepros](http://alphapixels.com/prepros/). Windows. Free.
    - [Scout](http://mhs.github.io/scout-app/). Mac & Windows. Free.

### 3. Customize SassyGuides:

- The [sassyguides.scss](http://github.com/alehandrof/sassyguides/blob/master/sass/sassyguides.scss) stylesheet combines all the other components. It's therefore a good place to start.

- The settings files &ndash; [base/\_settings.scss](http://github.com/alehandrof/sassyguides/blob/master/sass/base/_settings.scss) and [libguides/\_settings.scss](http://github.com/alehandrof/sassyguides/blob/master/sass/libguides/_settings.scss) &ndash; are also good starting points. You can override settings by adding them in new file and importing it into `sassyguides.scss`.

### 4. Use SassyGuides:

#### Locally

To work locally, download some LibGuides pages and then edit the HTML files to add `<link rel="stylesheet" href="path/to-your/sassyguides/sassyguides.css">` just before the `</head>`. Make sure they don't include any CSS apart from the default LibGuides stylesheets.

#### Online

- Upload the compiled stylesheet (`sassyguides.css`) to your institution's servers, LibGuides (use a "Documents & Files" box) or a CDN. (At a pinch Dropbox will do, but it's not very fast.)
- Link to the stylesheet: `<link rel="stylesheet" href="//yourserver.com/sassyguides.css">`

---

### Recommended Ruby Environment

The environment I use to develop SassyGuides combines Ruby, Guard, Compass & LiveReload. The idea is to have Guard watch the SassyGuides directory so that it will re-compile the Sass when you edit it and then call LiveReload to refresh your browser. There are instructions on how to set this and similar workflows around the web but, while the outline below is from memory and rather inelegant, it should get you there. Feel free to ask me for help if you get stuck.

* Install LiveReload:
    - Install the [LiveReload extension](http://feedback.livereload.com/knowledgebase/articles/86242-how-do-i-install-and-use-the-browser-extensions-) on the browser you'll be using for development.
* Install Ruby:
    - _Windows_ &ndash; http://rubyinstaller.org/
    - _Linux_ &ndash; `sudo apt-get install ruby`
    - _Mac_ &ndash; Already installed
* Install the required Ruby gems:
    - `gem install guard-compass guard-livereload`
    - On _Linux_ you will need to add `sudo` before the above command.
* Test it out:
    - Run `guard` in the SassyGuides directory.
    - Depending on your OS, you may be asked you to install some more gems. Exit guard (by typing `e` and <kbd>Enter</kbd>) and install them (`gem install whatever`).
    - Repeat until you don't get any errors :)
* Use it:
    - Run `guard` in the SassyGuides directory.
    - Open a local HTML file that links to the _compiled_ SassyGuides (`sassyguides.css`).
    - Start hacking SassyGuides!
