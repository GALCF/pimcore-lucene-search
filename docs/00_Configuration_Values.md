# Configuration

Here you'll find all the configuration possibilities, default values and also some description.

| Name | Type | Default | Description |
|------------------------------------------|------|----------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| enabled | bool | false | Enable and configure the search frontend if you want to include a full text search on your website. |
| fuzzy_search_results | bool | false | Fuzzy search results: When enabled, a fuzzy search is performed. The search will automatically include related terms. |
| search_suggestion | bool | true | Search suggestions: When enabled, a fuzzy search for similar search terms is performed. If no results could be found for the search term entered by the user, similar search terms are presented as suggestions. |
| own_host_only | bool | true | Own Host only: Limit search (and crawling) results to results from the current seed (sub-)domain only. |
| allow_subdomains | bool | false | Allow Subdomains: Limit search (and crawling) results to allow / disallow subomdains of current seed. |
| seeds | array | [] | Start-Urls (Seeds): Specify start URLs for the crawler. Please enter with protocol! e.g. http://www.pimcore.org and enter a starting URL on your main domain first and any other domains next. |
| categories | service | ~ | If search results should be displayed by categories, please enter all valid categories here. The crawler sorts a page into a category if it contains a html meta tag with the name "`lucene-search:categories`". |
| filter:allow_query_in_url | bool | false | When true, LuceneSearch will crawl urls with query fragments. |
| filter:allow_hash_in_url | bool | false | When true, LuceneSearch will crawl urls with hash fragments. |
| filter:valid_links | array | [] | Regex for valid Uris: Specify PREG regexes with start and end delimiter to define allowed links. e.g. `@^http://www\.pimcore\.org*@i` |
| filter:user_invalid_links | array | [] | Regex for forbidden Uris: Specify PREG regexes for links which should be ignored by the crawler. The crawler does not even follow these links e.g. `@^http://www\.pimcore\.org\/community*@i` |
| allowed_mime_types | array | ['text/html', 'application/pdf'] | Supported: `text/html`, `application/pdf` |
| allowed_schemes | array | ['http'] | Define which url Schemes are allowed. (eg. http and/or https). Default is http. |
| crawler:max_link_depth | int | 15 | To avoid loops produced by relative links on a website, a maximum link depth needs to be set. Please choose the value suited to the website to crawl. |
| crawler:max_download_limit | int | 0 | Maximum links to crawl: Constrain crawler to a specific limit of crawled links. Defaults is 0 which means no limit. |
| crawler:content_max_size | int | 0 | Maximum content size (in MB): crawler ignores resources if its size exceeds limit (mostly useful for asset indexing). Defaults is 0 which means no limit. |
| crawler:content_start_indicator | string | ~ | You can limit the page content relevant for searching by surrounding it with certain html comments. The crawler will still parse the entire page to find links, but only the specified area within your html comments is used when searching for a term. String specifying content start for search. |
| crawler:content_end_indicator | string | ~ | String specifying content end for search. |
| crawler:content_exclude_start_indicator: | string | ~ | String specifying exclude content start for search. |
| crawler:content_exclude_end_indicator | string | ~ | String specifying exclude content end for search. |
| locale:ignore_language | bool | false | Receive search results from all languages, set to false to limit search results to the current language only. The current language is retrieved from the registry, the language of any page in the search result index is extracted by the crawler (Content-Language Http header, html tag lang attribute or html meta tag content-language) |
| locale:ignore_country | bool | true | Receive search results from all countries, set to false to limit search results to country only. The current country is retrieved from the search result index. it is extracted by the crawler (html meta tag country) |
| restriction:enabled | bool | false | Document Restriction: Ignore Document restrictions. Set to true if you're using the [Pimcore/MembersBundle](https://github.com/dachcom-digital/pimcore-members) |
| boost:documents | int | 1 | Document Boost Factor |
| boost:assets | int | 1 | Asset Boost Factor |
| view:max_per_page | int | 10 | Max Results per Page |
| view:max_suggestions | int | 10 | Max Suggestions |