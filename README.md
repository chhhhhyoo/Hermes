# Hermes
Trending news article you should not miss

## Modules Overview 
```
+--------------------+       +-------------------+       +--------------------+
| News Source Crawler| --->  | Article Clustering| --->  |  Summarization     |
| (Newspaper3k / API)|       | (SBERT + HDBSCAN) |       |  (BART / Pegasus)  |
+--------------------+       +-------------------+       +--------------------+
        |                             |                             |
        v                             v                             v
+--------------------+       +-------------------+       +--------------------+
|  Raw News Storage  |       | Cluster DB (Topic)|       |  Summary Storage   |
|  (PostgreSQL / S3) |       | ID, Titles, Links |       |  Summary, Sources  |
+--------------------+       +-------------------+       +--------------------+

       \______________________________________________________________/
                                      |
                                      v
                         +--------------------------+
                         |     FastAPI Backend      |
                         | (serve JSON summaries)   |
                         +--------------------------+
                                      |
                                      v
                         +--------------------------+
                         |    React / Flutter UI    |
                         | (3-sentence news cards)  |
                         +--------------------------+
```