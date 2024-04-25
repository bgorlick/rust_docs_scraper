# Rust Documentation Scraper

`rust_docs_scraper` is a multithreaded Rust/Web-Based HTML Documentation Scraper and Formatter designed to scrape and format documentation from the docs.rs website. This tool is intended for educational purposes and facilitates easier analysis and processing of Rust documentation. The actual codebase of this variant is written in python, so if you came here looking for a web scraping tool that is written in the actual language of rust, apologies. You can however use this tool to easily view the rust docs and build your own tools in rust. 

The current design allows scraping of the docs.rs site, however, you can easily modify it to work with your own local rust documentation.


## AI and Machine Learning Potential for Rust Software Development
One of the reasons for this tool is to more easily transform rust documentation into data formats that can be easily used for machine learning dataset training, or inference. With a small amount of effort, the outputs and database can be easily accessed by toolchains that AI models use, to provide the model with easy to parse documentation without a web browser.


## Installation

Install this package using pip:

```bash
pip install rust_docs_scraper
```


## Uniquely Powerful HTML Stripping and Parsing
The html stripping and parsing is a very useful aspect of this tool. A lot of regex tricks are applied to take a heavily formatted html document and reduce it down into an easily readable plaintext variant in the 'stripped_html' options. 

## Installation

Install this package using pip:

```bash
pip install rust_docs_scraper
```

## Features

- Scrapes Rust documentation for specified crates and versions.
- Stores data in a SQLite database for further analysis.
- The database can be easily queried by crate/version
- The database can store documentation for every version of a crate.
- Provides command-line interfaces for interactive use and automation.
- Capable of handling multiple versions simultaneously.
- Strips and formats HTML content to be more readable and processable.


Usage
-----

Here's a simple exmaple of how you can use `rust_docs_scraper`:
`python -m rust_docs_scraper regex --all --database -v -V 1.9.5`

This command scrapes documentation for the regex crate, version 1.9.5, saves the data to a database.

Follow this command with something like this to query the database for the stripped down version:
```bash
sqlite3 rust_docs.db "SELECT url, stripped_html from sub_pages WHERE crate_name = 'regex' AND crate_version = '1.9.5' AND url = 'https://docs.rs/crate/regex/1.9.5/'"`
```


### CLI Options

*   `-m, --modules` Print module URLs.
*   `-a, --macros` Print macros and their descriptions.
*   `-s, --structs` Print structs and their descriptions.
*   `-e, --enums` Print enums and their descriptions.
*   `-f, --functions` Print functions and their descriptions.
*   `-t, --types` Print types and their descriptions.
*   `-d, --database` Save the collected data to a SQLite database.
*   `-v, --verbose` Print detailed descriptions.
*   `-V, --version` Specify the version(s) to fetch.
*   `-l, --limit` Limit the number of items printed.
*   `-x, --filter` Filter items based on a regular expression pattern.
*   `-o, --output` Output the results to a file.
*   `-w, --workers` Maximum number of worker threads.
*   `--db-name` Specify the name of the SQLite database file.
*   `--db-path` Specify the path for the SQLite database file.
*   `--all` Print all available information.
*   `--details` Print the full HTML content of a specific item.

Contributing
------------

Contributions are welcome! Please feel free to submit pull requests or open issues to improve the functionality or documentation of this tool.

License
-------

This project is licensed under the MIT License - see the LICENSE file for details.


