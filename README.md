# google-custom-search

[![Downloads](https://pepy.tech/badge/google-custom-search)](https://pepy.tech/project/google-custom-search)

# How to use this package.

## Next version can search image.

## first please install this package
```bash
pip install google-custom-search
```
or if you want use async/await, please install.
```bash
pip install google-custom-search[async]
```

## sample code
```py
import google_custom_search

google = google_custom_search.custom_search(apikey="your api_key", engine_id="your engine_id")
# if image is True, it's can search, but you need to setting at google console search

results = google.search("Hello")

for result in results:
    # get a title.
    print(result.title)
  
    # get a link.
    print(result.url)
  
    # get a displayLink.
    print(result.displaylink)

# get a list of htmlTitle.
for i in result.html_titles:
    print(i)
  
# get a list of snippet.
for i in result.snippets:
    print(i)
```

## sample code async version
```py
import asyncio
import google_custom_search

google = google_custom_search.custom_search(token="your api_key", engine_id="your engine_id", image=True)
# if image is True, it's can search, but you need to setting at google console search

async def main():
    result = await google.search_async("word!")
    for i in result.titles:
        print(i)
    for i in result.urls:
        print(i)
    for i in result.display_urls:
        print(i)
    for i in result.html_titles:
        print(i)
    for i in result.snippets:
        print(i)
    
loop = asyncio.get_event_loop() 
loop.run_until_complete(main())
```
