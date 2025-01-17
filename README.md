# LocalGov Drupal News

Provides the pages and navigation for presenting news articles. A part of the LocalGovDrupal distribution.

## What is in it?
- 2 x Content types:
  - News article - a single news article, optionally categorised.
  - Newsroom - a landing page to list and feature news articles (sub-module).
- 1 x Media type:
  - News default image - provides a library of pre-defined images for use in news articles.
- 3 x blocks:
  - News search form.
  - Featured news displaying up to 3 featured or promoted news articles (part of Newsroom).
  - News article feed, an ajax loader for news articles (part of Newsroom).

## Install process
- Standard Drupal module installation process applies.  But...
- The 3 x block configuration files are only installed if you are using the LocalGov Drupal base theme.  So *before* installing this module, open these three files and replace "localgov_theme" with your theme name:
  - config/optional/block.block.localgov_news_search.yml
  - modules/localgov_newsroom/config/optional/block.block.localgov_featured_news_articles.yml
  - modules/localgov_newsroom/config/optional/block.block.localgov_news_articles_feed.yml

  You can revert these changes after module installation as these files are no longer needed.
- Alternatively, add these three blocks from the Drupal block layout admin page:
  - The "News Search" block can be placed in a second sidebar region.
  - The "Featured News" block should be placed in Content Top or at the top of the main content region.
  - The "News Article Feed" block should be placed in the main content region.

## Usage
- Add default news images (optional).
- Add news articles. By default:
  - The Categories field uses the LocalGov Topics vocabulary. Edit the field to use alternative or additional vocabularies.
  - Image is a required field - authors can either select a pre-defined default news image (see above), upload a new image, or select an image from the media library.
  - Article nodes are not promoted - see the Featured News section below.
  - Article aliases are: news/[node:localgov_news_date:date:html_year]/[node:title]
- If the Newsroom module is installed:
  - Add a newsroom, with alias /news
  - Select up to 3 featured articles.
  - The Featured News block shows up to 3 featured articles - if there are fewer than 3 explicitly featured articles the remainder will be filled by the latest promoted articles (if any).
  - The Article Feed block will show 10 articles excluding those in the featured block, and load the next 10 when 'Show more' is clicked. The link will be hidden if there are no more articles to show.

