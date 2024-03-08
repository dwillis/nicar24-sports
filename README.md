# Bringing data journalism to the sports section

### THIS REPO: https://github.com/dwillis/nicar24-sports

Materials for this NICAR 2024 session.

* Matt Waite, University of Nebraska
* Derek Willis, University of Maryland
* [Sapna Bansil](https://cnsmaryland.org/youth-football/), University of Maryland [slides](https://docs.google.com/presentation/d/1Up9vq7Z_Su7cKKwasnX3IcOts4xr7B2OlgTZGNMqvCs/edit#slide=id.g2c0d3838e6d_2_181)

### Resources

* [Sports DataVerse](https://sportsdataverse.org/)
* [Sports Data Analysis and Visualization](https://www.thescoop.org/sports/)
* [Using R Packages to get data](https://www.thescoop.org/sports/usingpackages.html)

### Examples

* [Behind the Minnesota Vikings' Wild Season](https://www.startribune.com/a-look-at-the-data-behind-the-minnesota-vikings-wild-unpredictable-season/600241956/)

We wanted a story that would especially appeal to our digital readers that heavily used data and graphics to look back at the Vikings' crazy season, just as they were heading into a playoff game. The biggest piece on this story were the play-by-play win probability charts, which is from data that you can pull using the espnscrapeR package. (My [video tutorials](https://sites.google.com/view/mj-basic-data-academy/intro-to-r/getting-nfl-data?authuser=0) show how to do that for one or multiple games.)

I also used play-by-play data downloaded with the espnscrapeR package to look at the point differential at the end of each quarter. The play by play data is super useful because it not only shows every play, but also has a record for the end of each quarter, the two-minute warnings and you can also find the start of overtime.

* In November, we also published [this data-heavy piece on the Vikings](https://www.startribune.com/9-charts-that-show-the-minnesota-vikings-stunning-turnaround-from-last-season/600227084/). It also leaned heavily on the win probability data. We also used some NFL NextGen stats to look at average separation stats for Justin Jefferson. You can get that data with this little snippet: 

```
receiving_next_gen <-  load_nextgen_stats(
  seasons = TRUE,
  stat_type = "receiving",
  file_type = getOption("nflreadr.prefer", default = "rds")
)
```

And then we also got passing stats on Kirk Cousins that show how often he was throwing into tight coverage (known as "aggressiveness")
You can get that data with this: 

```
passing_next_gen <-  load_nextgen_stats(
  seasons = TRUE,
  stat_type = "passing",
  file_type = getOption("nflreadr.prefer", default = "rds")
)
```

* [Justin Jefferson piece](https://www.startribune.com/justin-jefferson-minnesota-vikings-statistics-all-pro-mvp-randy-moss/600247729/?refresh=true), February 2023:  
Most of this is just high-level stuff taken from various websites, but there are two pieces where we pulled data from an API using R. The main one is the bubble chart that shows how Jefferson led the team on offensive yards (There is a nifty package called "[packcircles](mimestream://messagethread/p448483/message/p511829?UUID=52FF0A60-4ECD-493C-B780-C97901E30DF2&loadRemoteResources#https://r-graph-gallery.com/305-basic-circle-packing-with-one-level.html)" that works with plotly package to make a bubble chart. The one in our story was made with other technology, though).  I also pulled the receiving yards per game data from the espnscrapR package, play by play data.

* [For Players, Scoring Matters. But Shouldn’t Other Things Too?](https://sash-wat.github.io/JOUR479XSite/_site/posts/soccer-analysis/)
* [For WVU, There’s No Place Like Home](https://herhoopstats.substack.com/p/for-wvu-theres-no-place-like-home)
