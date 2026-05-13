# Podcast XML Generator

*This Project follows the Career Essentials in GitHub Professional Certificate course through LinkedIn Learning.*

Certificate:



## About

This GitHub Action converts a YAML file to XML for a podcast feed.

## Usage

Example: https://github.com/n-smith-byu/podcast-test/

### 1. Turn on GitHub Pages

In your repository, so to Settings > Pages and select the main branch as the source. This will create a link to your page and give all of the content in the main branch a URL. Note the URL for the next step.

### 2. Create a YAML File

Create a YAML File with the following format:

```yaml
title: The Future in Tech
subtitle: Powered by LinkedIn Learning
author: Ray Villalobos
description: Conversations with leaders building next generation technology tools.
image: /images/artwork.jpg
language: en-us
category: Technology
format: audio/mpeg
link: https://n-smith-byu.github.io/podcast-test
item:
  - title: EP01-What's Happening in 2023
    description: Ray Villalobos and Content Managers Natalie Pao and Simon St. Laurent discuss what 2023 holds for the future in technology.
    published: Thu, 12 Jan 2023 18:00:00 GMT
    file: /audio/TFIT01.mp3
    duration: 00:00:36
    length: 576,324
  ...Repeat for each episode
```

### 3. Sample Workflow:

You will need to create a workflow in GitHub Actions:

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
