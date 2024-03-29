# Jekyll Doc Theme

Go to [the website](https://aksakalli.github.io/jekyll-doc-theme/) for detailed information and demo.

## Running locally

You need Ruby and gem before starting, then:

```bash
# install bundler
gem install bundler

# clone the project
git clone https://github.com/aksakalli/jekyll-doc-theme.git
cd jekyll-doc-theme

# run jekyll with dependencies
bundle exec jekyll serve
```

## If bundle exec jekyll serve fails

It could be that the bundler version is not the right one :
look at the "BUNDLE WITH' and version of bundler in the `Gemfile.lock` file:

```
BUNDLED WITH
   2.0.1
```
and in that case use : 

```bash
gem install bundler -v '2.0.1'
```

## Docker

Alternatively, you can deploy it using the multi-stage [Dockerfile](Dockerfile)
that serves files from Nginx for better performance in production.

Build the image for your site's `JEKYLL_BASEURL`:

```
docker build --build-arg JEKYLL_BASEURL="/your-base/url" -t jekyll-doc-theme .
```

(or leave it empty for root: `JEKYLL_BASEURL=""`) and serve it:

```
docker run -p 8080:80 jekyll-doc-theme
```

## License

Released under [the MIT license](LICENSE).
