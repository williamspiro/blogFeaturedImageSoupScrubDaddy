# blogFeaturedImageSoupScrubKitten
A tool to soup featured images from an external blog, and set them as the featured image for their HubSpot hosted equivalent post if the import does not go as planned. This tool will find the featured image on your external blog, upload it to the HubSpot File Manager, and then set the HubSpot hosted version of the posts' `featuredImage` with the newly uploaded File Manager asset.

### REQUIRES
[python](https://www.python.org/)  
[BeautifulSoup](https://www.crummy.com/software/BeautifulSoup/bs4/doc/)  
[requests](http://docs.python-requests.org/en/master/)  

### SETUP
Set required variables `portalId`, `accessToken`, `blogRootUrl`, `featuredImageSelector` & `postsToSoupScrubKitten`

1. __portalId__ - HubSpot portal ID (ex. `1234`)  
2. __accessToken__ - Access token generated for __portalId__ (ex. `1234-5678-9123-456-789`)  
3. __blogRootUrl__ - The external blogs root url (ex. http://www.blogrooturl.com/)  
4. __featuredImageSelector__ - The CSS selector which select the external blogs featured image (ex. `.featured-image img`)  
5. __postsToSoupScrubKitten__ - A python list of the slugs of all of the external posts to soup (ex. `["slug/post/1", "slug/post/2", "slug/post/3"]`)  

It is important that the post slugs of the external and HubSpot posts are the same. `blogRootUrl` + `postsToSoupScrubKitten[slugs]` should equal the actual URL of the posts. `slug`s should not start with a `/`, rather, `blogRootUrl` should end with a `/`

### TO RUN
cd to the `blogFeaturedImageSoupScrubKitten` directory. Run:
```
$ python blogFeaturedImageSoupScrubKitten.py
```

