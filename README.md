# MOSFIRE Web Page

An mkdocs port of the MOSFIRE instrument web page.

The docs can be built on any machine with the necessary packages ... (need to set up mkdocs environment on the build machine).

If needed, edit the `mkdocs.yml` file to edit the navigation menu, then run `mkdocs build` to build the HTML files in the `site/` directory.  To deploy the updated content to the Keck web site, rsync those contents to the web server: `rsync -av site/* rastro@www:/www/public/realpublic/inst/mosfire/`.  The site is also deployed to github using `mkdocs gh-deploy` which results in a copy of the web site at [https://KeckObservatory.github.io/MOSFIRE-Web-Page/](https://KeckObservatory.github.io/MOSFIRE-Web-Page/).
