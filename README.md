To generate the site:
> jekyll b --watch

To push it to the server:
> rsync -azv --delete _site/ visionscarto.net:/var/alternc/html/v/visionscarto/spip/observable-jekyll/
