# Michael Basinski's Book Reviews

[Michael Basinski](https://www.poetryfoundation.org/poets/michael-basinski) contributed nearly 300 reviews of poetry publications to a webzine called <cite>[The Hold](https://web.archive.org/web/20090301055656/http://the-hold.com:80/index1.html)</cite>, from 2000-2005. He was the Associate Curator of [The Poetry/Rare Books Collection SUNY at Buffalo](https://library.buffalo.edu/pl/about/).

The reviews describe the works of poets and publishers at a time right before the web became ubiquitous, so they are a useful archive as well as an enjoyable read.

Copyright (c) 2005 Michael Basinski. Reproduced here and released under MIT License with permission of the author.

Usage
-----

The `index.md` should be a perfectly workable way to read through the book reviews, using any text editor or markdown viewer.

You can build an html version, to include a table of contents using [Jekyll](https://jekyllrb.com/) and the command `jekyll serve`. Results will look something like the page at https://nocategories.net/basinski-book-reviews/

You can build an EPUB version using
```bash
pandoc -o michael-basinski-book-reviews.epub index.md  --epub-cover-image=basinski-reviews-cover.png --toc
```
to get something like https://nocategories.net/assets/epub/michael-basinski-book-reviews.epub

## TODO

- [x] one file per review
- [ ] yaml data for title, author, desc
- [ ] yaml data for isbn, issn
- [ ] yaml data for publisher
- [ ] eventually.. contribute book records to openlibrary.org

Potential Upgrades
----------------------

Any other ideas from the community? 

Most links' URLs are outdated, so they've all been repointed to archived versions, but in some cases there may be newer links to information about the books, on google books perhaps, or worldcat, etc.

Normalize the title of each review. Probably best to use simply "{book} by {author}" since that's already most common.

Structuring the book data into YAML or JSON would allow for embedded metadata, which in turn could provide better search visibility for these rare books. Something like this perhaps:
```html
<script type='application/ld+json'>
{
  "@context": "http://schema.org/",
  "@graph":
  [
    {
      "@type": "Book",
      "isbn": "00000000",
      "name": "title of book",
      "author": {
        "@type": "Person",
        "name": "Jene du Toit"
      },
      "numberOfPages": "99",
      "datePublished": "2000",
      "offers": {
      "@type": "Offer",
      "price": "6.99",
      "priceCurrency": "USD"
      },
      "publisher": {
        "@type": "Organization",
        "name": "publisher name",
        "address": "publisher address",
        "url": "http://www.example.com/",
        "email": "test@example.com"
      },
      "review": {
      "dateCreated": "2000-01",
      "author": "reviewer fullname",
      "reviewBody": "text of review"
      }
    }
  ]
}
</script>
```
