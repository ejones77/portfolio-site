---
title: Wikipedia Web Scraping with Go
description: Set up a data structure with nested hyperlink references 
date: "2024-02-04"
jobDate: 2024-02-04
work: [Web Scraping]
techs: [Go]
thumbnail: ../../images/Wikipedia-logo-v2.svg.png
projectUrl: https://github.com/ejones77/go_scraper/tree/main

---

A lightweight wikipedia scraper built in Go that produces a comprehensive JSON structure that captures every text element and its relationships:

```json
{
  "Title": "Example Article",
  "Sections": [
    {
      "Title": "Introduction",
      "Paragraphs": [
        {
          "Text": "This is the first paragraph of the introduction.",
          "Links": [
            {
              "Text": "Example Link",
              "URL": "https://example.com"
            }
          ]
        },
        {
          "Text": "This is the second paragraph of the introduction.",
          "Links": []
        }
      ]
    },
    {
      "Title": "Main Section",
      "Paragraphs": [
        {
          "Text": "This is the first paragraph of the main section.",
          "Links": []
        }
      ]
    }
  ],
  "References": [
    {
      "Id": "cite_note-6",
      "Text": "This is the first reference.",
      "Links": [
        {
          "Text": "Reference Link",
          "URL": "https://reference.com"
        }
      ]
    }
  ]
}
```