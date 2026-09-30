# Library Management System

A small command-line library management system written in C. It lets a user manage a collection of books, search the catalog, and save changes to a text file.

## Features

- Login using credentials stored in `credentials.txt`
- Add, delete, and modify book records
- Look up a book by its 13-digit ISBN
- Search titles by a text fragment
- Display books sorted by title, price, or publication date
- Save catalog changes to `books.txt`
- Validate ISBN format, duplicate ISBNs, quantities, prices, and publication dates

## Requirements

- A C compiler such as GCC
- A terminal or command prompt

## Build and run

Run these commands from the project directory so the program can find `books.txt` and `credentials.txt`:

```sh
gcc FinalP.c -o library-system
```

On Windows, run the resulting executable with:

```powershell
.\library-system.exe
```

On Linux or macOS, run it with:

```sh
./library-system
```

Choose **Login** at the welcome screen and enter the username and password stored in `credentials.txt`.

## Data files

The program expects both data files in its current working directory.

`books.txt` stores one book per line using this comma-separated format:

```text
ISBN,Title,Author,Quantity,Price,Month-Year
```

For example:

```text
9700000000001,data structures and algorithms,Timberlake Karen,10,7.5,12-2008
```

The publication month is a number from 1 to 12. `credentials.txt` stores the username on the first line and the password on the second line.

Changes are held in memory until **Save** is selected. Choosing to quit without saving discards unsaved changes.

## Security note

Credentials are stored as plain text, and this project is intended for learning and demonstration. Do not use real or reused passwords. Replace the sample credentials before sharing the repository, or remove the credentials file from public version control.

## Limitations

- The program stores up to 100 books in memory.
- Search by title is case-sensitive.
- The text-file format uses commas as separators, so titles and author names should not contain commas.
