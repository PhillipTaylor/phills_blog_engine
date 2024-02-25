
# A client-side blog engine.

Create blog posts in the easy markdown format.

Have a lightweight, low resource nginx instance serve the content as-is, or use your own nginx server with no modifications required.

The index.html will download and render the markdown making a simple, effective HTML website. Fork this repo, put your own styles and
side links on 

## Rationale

I created and hosted my own blog on my own website for the last decade. I self hosted the Wordpress docker instance and associated MySQL db and now I realise I want something that's just as minimal in terms of resources as possible. I run 5+ websites so cutting down resources and reducing the number of Wordpress instances running adds up.

With this template, your website can be served by an nginx or apache instance. The engine is simply an HTML page. It uses client-side Ajax to fetch markdown content and renders the contents in HTML the client's browser. This gives you the ease of writing markdown on the server but without requiring any complex server side configuration.

## How to use it

1. Create your pages under html/posts/
2. Add any assets such as images.
3. Set nginx to serve the index.html and any assets

## What index.html does/doesn't do.

The sidebar is not automatically generated, you must edit it yourself.
You must edit the index.html page to add your own styles.
The index.html file will automatically fetch files under /post/ and convert them to HTML.

## How to test and develop your site locally

```bash
docker build -t blog .
docker run -it --publish 1200:80 blog
```
Check the output at http://localhost:1200/

## How to deploy your site.

Simply copy your html file to nginx/apache's html directory and it will work. No database, special tools required.
