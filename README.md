# Product Review Web App

This is a Flask coursework application for collecting and examining product reviews. A user supplies a product identifier, and the application parses review fields, prepares the data and presents it through browser pages and export routes.

The route handlers are in [app/routes.py](app/routes.py). Parsing and conversion helpers are in [app/utils.py](app/utils.py). The separate [analysis notebooks](https://github.com/oldprize47-SH/ceneo-review-analysis) cover the related notebook workflow.

## Running locally

The historical entry point is `python run.py`. Dependencies are recorded in [requirements.txt](requirements.txt), but that environment has not been freshly installed. Some packages are platform-specific.

The original application starts its development server during import and enables debug mode. It needs adjustment before deployment. The Python files were checked for syntax; the server, scraper and translation requests were not run during this portfolio update.

The reviews and product content belong to their original authors and platform. This copy preserves the public course archive and does not add newly collected reviews.

[Original repository](https://github.com/sangheon47/CeneoWebScraperSH). Original history and attribution are retained.
