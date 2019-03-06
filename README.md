# Timetables_Crawler

### Overview

This web crawler is only for demonstration purposes of the [Scrapy 1.6 documentation](https://docs.scrapy.org/en/1.6/index.html).

The task is to extract timetables of all the venues in the University of Sydney during 2019.

__It should be noted that the target website use the [Robots exclusion standard](https://en.wikipedia.org/wiki/Robots_exclusion_standard) to limit all areas of it should not be processed by web robots.__

### Example

The script `./example_spider.py` is based on the code in the chapter, [Scrapy at a glance](https://docs.scrapy.org/en/1.6/intro/overview.html#walk-through-of-an-example-spider).

The spider can be ran by using `runspider` command in the directory of repository:

```shell
scrapy runspider example_spider.py -o items.json
```

And it will regenerate a file `./items.json` , which contains those items in blue tables on [the example website](https://web.timetable.usyd.edu.au/menu.jsp?siteMap=true).

### Venues

The script `./Timetables_Crawler/spiders` is used to extract `(Venue, VenueId)` pairs, which would be parts of the `start_urls` later.

The spider can be ran by this command:

```shell
scrapy crawl venues -o venues.json
```

And it will regenerate a file `./venues.json`, which can found in the `./`.

### Timetables

The script `./Timetables_Crawler/spiders` is used to extract all specific timetables, which can be parsed by `pandas`.

The spider can be ran by this command:

```shell
scrapy crawl timetables -o timetables.json
```

And it will regenerate a file `./timetables.json`, which is not contained in the repository on the GitHub.

### Parse

The script `./parse.py` is used to parse the `timetables.json`. It is really simple.

It is really simple and can be ran by:

```shell
python parse.py
```

