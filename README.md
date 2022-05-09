# Michael Basinski's Book Reviews

[Michael Basinski](https://www.poetryfoundation.org/poets/michael-basinski) contributed nearly 300 reviews of poetry publications to a webzine called <cite>[The Hold](https://web.archive.org/web/20090301055656/http://the-hold.com:80/index1.html)</cite>, from 2000-2005. He was the Associate Curator of [The Poetry/Rare Books Collection SUNY at Buffalo](https://library.buffalo.edu/pl/about/).

The reviews describe the works of poets and publishers at a time right before the web became ubiquitous, providing a useful archive and an enjoyable read.

Copyright (c) 2005 Michael Basinski. Reproduced here and released under MIT License with permission of the author.

Usage
-----



## TODO

- [x] one file per review
- [ ] yaml data for title, author,
- [ ] yaml data for links to book, author info, where possible.
- [ ] yaml data for isbn, issn
- [ ] yaml data for publisher
- [ ] eventually.. contribute book records to openlibrary.org?

Potential Upgrades
----------------------

Any other ideas from the community?

Most links' URLs are outdated, so they've all been repointed to archived versions, but in some cases there may be newer links to information about the books, on google books perhaps, or worldcat, etc.

Normalize the title of each review. Probably best to use simply "{book} by {author}" since that's already most common.

Structuring the book data into YAML or JSON would allow for embedded metadata, to provide better search visibility for the books. A template:

```json
{
  "@context": "https://schema.org/",
  "@type": "CriticReview",
  "datePublished": "2000-01",
  "reviewBody": "text of review",
  "description": "use the cite info from yaml",
  "publisher": "The Hold",
  "url": "#",
  "author": {
    "@type": "Person",
    "name": "Michael Basinski",
    "SameAs": [
      "https://en.wikipedia.org/wiki/Michael_Basinski",
      "https://www.poetryfoundation.org/poets/michael-basinski",
      "http://www.ubu.com/contemp/basinski/index.html",
      "https://jacket2.org/content/michael-basinski"
    ]
  },
  "itemReviewed": {
    "@type": "Book",
    "isbn": "00000000",
    "name": "title of book",
    "author": {
      "@type": "Person",
      "name": "book author",
      "sameAs": "#"
    },
    "numberOfPages": "99",
    "datePublished": "2000",
    "publisher": {
      "@type": "Organization",
      "name": "publisher name",
      "address": "publisher address",
      "url": "http://www.example.com/",
      "email": "test@example.com"
    }
  }
}
```
