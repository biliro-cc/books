
# Langduet Book Repo

Public domain books created or sourced for [langduet.com](https://langduet.com).

## The structure of this repo

Each language has its own folder. For instance, `latin`. 

Inside these folders, each book has a folder. For instance, `aeneid`.

Inside this folder, there are always two folders: `foreign`, and `english`. These are the two epubs stored for this book. Note that these epubs are unzipped (epubs are really zip files).

At the root of the repo is a single .json file named `book_information.json`. This is where metadata for each book is stored. Every book entry in the folder structure should be mirrored in this file, and vice versa.

Here's an excerpt from this file:

    [
      {
        "language": "latin",
        "books": [
          {
            "filename": "aeneid",
            "title": "The Aeneid",
            "author": "Virgil",
            "translator": "John Dryden",
            "english_source": "Standard Ebooks",
            "foreign_source": "Gutenberg",
            "verified": true,
            "description": "Virgil\u2019s epic poem begins with Aeneas fleeing the ruins of Troy with his father Anchises and his young son Ascanius, with a plan to make a home in Italy. Because of a prophecy foretelling that the descendants of Aeneas will one day destroy Carthage, Juno\u2019s favorite city, Juno orders the god of the winds to unleash a terrible storm. The ships are thrown off course and arrive at an African port. As Aeneas makes his way towards his new home he encounters Dido, Carthage\u2019s queen, and falls deeply in love. \u2014 Standard Ebooks",
            "last_commit": "ac30d6a0490ea00e70901ae0b2167778b9da3e8c",
            "last_commit_time": "2022-06-10T00:28:58.000Z",
            "first_commit": "ac30d6a0490ea00e70901ae0b2167778b9da3e8c",
            "first_commit_time": "2022-06-10T00:28:58.000Z"
          },
          ... (more books) ...
        ]
      },
      ... (more languages) ...
    ]
    
All of these fields should be filled out for a new book, besides `last_commit`, `last_commit_time`, `first_commit`, and `first_commit_time`. These will be filled out automatically once your pull request is accepted to the repository.

For descriptions we recommend using https://onlinestringtools.com/escape-string to store them in a .json string.

## Book verification

In order for a book to be marked as "verified" in the metadata file, it must meet the following criteria:

1. Clicking through the book using the shared left/right buttons must always land you on the same page in both books. This means that if you press the right arrow on your keyboard three times and hit chapter 1 in the English version, you should hit chapter 1 in the foreign version as well. [Calibre's](https://calibre-ebook.com/) built in ebook editor is great for accomplishing this. There's a "split page" button at the bottom of the preview pane, and dropping an `.html` or `.xhtml` file on top of another one in the file browser merges them.
3. The table of contents must be very close to identical; any structure or indents in one should be replicated in the other.
4. Any extra fluff should be removed. Corresponding pages should be close to identical on both sides in terms of content.
5. There should be no font-family, font-size, or line-height CSS tags applied to the main body text: it should appear as Times New Roman.
6. All verified books should have Langduet title pages; premade ones for various sources can be found at the [verified-titlepages](https://github.com/langduet/verified-titlepages) repo. Each of these is just a simple .xhtml file with no dependencies; you can just paste it into an existing titlepage to replace it and then edit the title and author text.
