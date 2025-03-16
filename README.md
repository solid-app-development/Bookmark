# Bookmark

Bookmark Apps

## Default Locations

### Directory

- /public/bookmark/

### Filename

- bookmark(.ext)

# Apps

## Solid OS


## Simple JSON

```json
{
  "@context": {
    "schema": "https://schema.org/",
    "ex": "https://example.org/ns#"
  },
  "@type": "ex:BookmarkCollection",
  "schema:name": "My Bookmarks",
  "schema:hasPart": [
    {
      "@type": "ex:Bookmark",
      "schema:name": "An Interesting Article",
      "schema:url": "https://example.com/article1",
      "schema:about": "Web3, RDF, and LLMs"
    },
    {
      "@type": "ex:Bookmark",
      "schema:name": "Solid and the Future of Web Decentralization",
      "schema:url": "https://example.com/article2"
    }
  ]
}
```


## PDS Interop

- https://pdsinterop.org/conventions/bookmark/
