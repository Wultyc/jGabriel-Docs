# Run the example site
To run the exampleSite from themes folder you just have to follow a few steps

1. Change your working dir to exampleSite
```bash
$ cd themes/hugo-book/exampleSite
```

2. Run the server
```bash
$ hugo server --minify --bind "0.0.0.0" --themesDir ../..
```

# Create a new project
On HUGO project root
```bash
$ hugo new docs/<project folder>/<project-name>/_index.md
```