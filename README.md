Scrapping Books Data from Book's ISBN
======================================
**In this article**
 * [Short Background](https://github.com/p4zaa/Chaloklum-Books/blob/main/Chaloklum-Books/README.md#short-background)
 * [Tools](https://github.com/p4zaa/Chaloklum-Books/blob/main/Chaloklum-Books/README.md#tools)
 * [Book's ISBN Collecting Process](https://github.com/p4zaa/Chaloklum-Books/blob/main/Chaloklum-Books/README.md#books-isbn-collecting-process)
 * [Collected Dataset](https://github.com/p4zaa/Chaloklum-Books/blob/main/Chaloklum-Books/README.md#collected-dataset)
 * [Problems and Obstacles Encountered](https://github.com/p4zaa/Chaloklum-Books/blob/main/Chaloklum-Books/README.md#problems-and-obstacles-encountered)

# Short Background
All books ISBN are all collected from my local bookstore.

**[Chaloklum Bookshop](https://dustyblu3.notion.site/dustyblu3/Chaloklum-Bookshop-We-sell-over-4000-second-hand-books-b29ecb72cd0f40f6812d96ae8e07eb5b)** is one of the bookstore in [Koh Phangan, Thailand](https://en.wikipedia.org/wiki/Ko_Pha-ngan) which selling over 4000+ second-hand books in many languages such as English, German, French ... etc. 

 Every year, there will be a large number of tourists visiting. Most of them are tourists from western countries. There are also many foreigners living and work here. This bookstore therefore sells books in a variety of languages. Almost all books are second-hand books. And there are frequent exchanges from foreigners who live here. You can bring your own books to exchange with the shop. 

This bookstore has been open for many years, but never recorded information about the book or any book trading information. So, I decided to collecting every books as possible in the store by using my phone to scanning every single book barcode for ISBN number and using python to retrieve information of the books from two sources, Google Books and Goodreads. 😃 

<img src="https://i.imgur.com/IVh3cZb.jpg" width="500"/>

## A complete code provides here
 * [Chaloklum-Books/Add_new_books_dataset.ipynb](Chaloklum-Books/Add_new_books_dataset.ipynb)

# Tools
Here are the lists of tools that I used
 ## Books ISBN Collecting
  * Android smart phone 
  * Application: 'Barcode to Text' by 1room
 ## Data Retrieving and Management Libraries
  * Python 3.8
  * NumPy 1.21.6
  * Json 2.0.9
  * BeautifulSoup 4.9
  * Requests 2.23
  * Pandas 1.3.5

# Book's ISBN Collecting Process
 - [X] Scanning all book's barcode in the bookstore using my smartphone and Barcode to Text application.
   - Barcode of the books represent the ISBN number.
   - Also during this step I do writing the code with some sample too.
 - [X] Export the ISBN number to .txt here an example how it look like.

  | books_isbn.txt |
  | --- |
  | 9784478048122 |
  | 9784478048009 |
  | 4091780326 |
  | 9784872577969 |
  | 4091780334 |
  | CIP2005001965 |
  | 6142204340028 |
  | ... |
 - [X] Use Python and some libraries as mentioned above to scrapped the webpage of the book given ISBN number.

# Collected Dataset
There are over 4000+ books but some books are too old, so there will be no information about it in both Google Books API and Goodreads

<details>
<summary><h4>Toggle to see an example of collected dataset table</h3></summary>

|    |   id |   isbn_10 |   isbn_13 |   isbn_other |     isbn_book | authors       | title                             | subtitle                                        |   publisher |   published_date |   page_count | categories                                                    | language   |   google_desc |   rating_avg |   #reviews |   #ratings |   #text_reviews |   thumbnail |   genre |   goodreads_desc |   text_reviews |   also_enjoy |   status |
|---:|-----:|----------:|----------:|-------------:|--------------:|:--------------|:----------------------------------|:------------------------------------------------|------------:|-----------------:|-------------:|:--------------------------------------------------------------|:-----------|--------------:|-------------:|-----------:|-----------:|----------------:|------------:|--------:|-----------------:|---------------:|-------------:|---------:|
|  0 |    1 |       nan |       nan |          nan | 9788020609564 | ['Jiří Šolc'] | Útěky a návraty Bohumila Laušmana | osud českého politika                           |         nan |             2008 |          403 | ['Political prisoners / Czechoslovakia / 1948-1968 / czenas'] | cs         |           nan |          nan |        nan |        nan |             nan |         nan |     nan |              nan |            nan |          nan |       -1 |
|  1 |    2 |       nan |       nan |          nan | 9789637253089 | nan           | A nők tartják az égbolt felét     | egy rendkívüli asszony rendkívüli élettörténete |         nan |             2005 |          nan | nan                                                           | hu         |           nan |          nan |        nan |        nan |             nan |         nan |     nan |              nan |            nan |          nan |       -1 |

</details>

I also do have a [notion page](https://dustyblu3.notion.site/Chaloklum-Bookshop-Books-Finder-beta-e4d5583000974436979ab191af02f25e) to find the book with this table too!

# Problems and Obstacles Encountered
 - Some books have no barcode(less than 5% of the books)
    > Some books doesn't even have the cover :'<
 - Some books have indistinct bar codes, covered with price tags, marked in dark ink.
    > Barcodes can still be scanned even if they are slightly damaged. <br />But will not be able to scan at all if the bar code is covered too much.
    
