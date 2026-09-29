# Product Review Web App

This is a Flask coursework application for collecting and examining product reviews. A user supplies a product identifier, and the application parses review fields, prepares the data and presents it through browser pages and export routes.

The route handlers are in [app/routes.py](app/routes.py). Parsing and conversion helpers are in [app/utils.py](app/utils.py). The separate [analysis notebooks](https://github.com/oldprize47-SH/ceneo-review-analysis) cover the related notebook workflow.

## Project goal

Make product reviews easier to explore by collecting them into a web interface with summaries, charts and exports.

![Project goal: ceneo-review-webapp](docs/goals/project-focus-v1.png)

AI-generated concept illustration. Device appearance, interface layout and example graphics are illustrative, not project photographs or measured results.

## Where it could be used

The workflow could help someone explore collected product feedback by reading review text alongside rating and recommendation distributions. Keeping structured review records also makes it possible to repeat an analysis without recollecting every page. The summaries describe the collected sample rather than all customers, and collection depends on the source site and permitted access.

## At a glance

![Ceneo review web application](docs/flowcharts/ceneo-web.png)

Overview reconstructed from the documented project and code. Results and verification limits are described below. [SVG](docs/flowcharts/ceneo-web.svg)

## From a product number to a review page

The extraction form passes a product ID to a Flask route. That route requests the product's review page, parses the review fields with BeautifulSoup and follows the next-page link until collection ends. The helper functions convert text fields such as ratings and recommendations into values that are easier to analyse. Translation helpers are also present for Polish review text.

The application stores review records and a product summary in JSON files. It then uses Pandas to compute review counts, average scores and rating/recommendation distributions, and Matplotlib to save charts for the browser pages. A product page presents a review table, while export routes provide JSON, CSV and XLSX downloads. The implementation uses local files for this workflow rather than a database-backed service.

## Reading the source

Start with [app/routes.py](app/routes.py) to follow form submission, collection, storage and the redirect to a product page. Read [app/utils.py](app/utils.py) alongside it to see the field selectors and transformations. The [templates](app/templates) show how the stored information is presented. The [notebook project](https://github.com/oldprize47-SH/ceneo-review-analysis) makes the collection and analysis steps easier to inspect separately.

This archive comes from Sangheon Park's 2024 exchange-student coursework at Krakow University of Economics. The routes, parsing helpers and templates form the application described above. The available records do not establish separate team roles or individual authorship of every supplied scaffold; no additional contributor split is inferred.

## Running locally

The historical entry point is `python run.py`. Dependencies are recorded in [requirements.txt](requirements.txt), but that environment has not been freshly installed. Some packages are platform-specific. Review that file in a separate Python environment before trying to recreate the setup. The source also depends on website markup and remote requests, so an environment that installs successfully is not enough to establish that extraction still works.

The original application starts its development server during import and enables debug mode. It needs adjustment before deployment. The Python files were checked for syntax; the server, scraper and translation requests were not run during this portfolio update.

The reviews and product content belong to their original authors and platform. This copy preserves the public course archive and does not add newly collected reviews.

[Original repository](https://github.com/sangheon47/CeneoWebScraperSH). Original history and attribution are retained.
