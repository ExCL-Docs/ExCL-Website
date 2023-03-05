# ExCL's Main Website

This repository contains the source for a Jekyll powered website for ExCL hosted at `Link Here`. If you have any questions about the source please contact Aaron Young at [youngar@ornl.gov](mailto:youngar@ornl.gov).

## Prerequisites

[Jekyll](https://jekyllrb.com/docs/installation/) must be install first before building the website.

Next the gems used by the site must be installed with 

    bundle install

## Serving the website locally for testing

In order to serve the website locally on a test server, with draft posts 
included, and with live reloading, use the command:

    bundle exec jekyll serve --drafts --livereload

## Deploying the website

In order to deploy the website, use the helper script `deploy.sh`.

## Updating Jekyll

In order to update Jekyll use `bundle update`

## Tools

- A create-thumbnails script is found in tools/create-thumbnails. It 
  can be used to create lower resolution thumbnails for use in a Jekyll 
  gallery.
