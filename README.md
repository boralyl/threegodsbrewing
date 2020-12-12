# threegodsbrewing

Three Gods Brewing Website and Blog

## Fresh Install

If you are doing a fresh install you will need to install ruby and ruby-dev.

```bash
$ sudo apt install ruby ruby-dev
```

Next install the `gitub-pages` and `bundler`.

```bash
$ sudo gem install github-pages bundler
```

Finally install.

```bash
$ bundle install
```

## Running Locally

```bash
$ bundle exec jekyll serve --incremental --drafts --watch --future
```

## Updating Gems and Theme

```bash
$ bundle update
```

## Images

Recommended image sizes for posts and recipes:

- Hero - 1600 x 650 px
- Thumb - 400 x 200 px
