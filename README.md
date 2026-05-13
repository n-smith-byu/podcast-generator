# Podcast XML Generator

*This Project follows the Career Essentials in GitHub Professional Certificate course through LinkedIn Learning.*

Certificate:
[Link](https://www.linkedin.com/learning/certificates/b242bd62206232b9159db18ec1efcc58a827d3e6369ffd0a7116e15172392c88?trk=share_certificate)


## About

This GitHub Action converts a YAML file to XML for a podcast feed.

## Usage

Example: https://github.com/n-smith-byu/podcast-test/

### 1. Turn on GitHub Pages

In your repository, so to Settings > Pages and select the main branch as the source. This will create a link to your page and give all of the content in the main branch a URL. Note the URL for the next step.

### 2. Create a YAML File

Create a YAML File with the following format:

```yaml
title: <Podcast Title>
subtitle: <Podcast Subtitle>
author: <Author Name>
description: <Podcast Description>
link: <GitHub Pages URL (from previous step)>
image: <Artwork Location>
language: <Podcast Language e.g. en-us>
category: <Podcast Category e.g Technology, https://podcasters.apple.com/support/1691-apple-podcasts-categories>
format: <format of files e.g. audion/mpeg>

item:
  - title: <Podcast Episode Title>
    description: <Podcast Episode Description>
    published: <Date Published e.g. Thu, 12 Jan 2023 18:00:00 GMT>
    file: <Filename e.g. /audio/TFIT01.mp3>
    duration: <duration e.g. 00:00:36>
    length: <length e.g. 576,324 (Get Info on your files)>
  ...Repeat for each episode
```

### 3. Sample Workflow:

You will need to create a workflow in GitHub Actions. Here is a sample:

```main.yaml
name: Generate Podcast Feeds
on: [push]
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout Repo
        uses: actions/checkout@v3
      - name: Run Feed Generator
        uses: n-smith-byu/podcast-generator@main
```
