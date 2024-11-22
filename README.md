# Japanese Vocabulary Extractor

This script allows you to automatically scan through various types of japanese media (currently manga and ebooks) and generate a csv with all contained words. It also allows you to automatically add the english definitions to the CSV.

The resulting csv can be imported to Anki (if you add the english definitions) or Bunpro.

# Installation

You need to have python installed (ideally Python 3.12).

Install the package using
```
pip install japanese-vocabulary-extractor
```

# Usage

```
jpvocab-extractor [-h] [--parent] [--add-english] --type TYPE input_path
```

Specify the type of media: 'manga', 'pdf', 'epub' or 'text'. Replace input_path with the path containing the files (or, if not a manga, the file directly). Make sure to surround it with quotation marks if there are spaces in the path! 

This will generate a vocab.csv file containing all words. If you wish to add definitions in the secon column of the CSV, add the "--add-english" argument.

Only for manga: If you enter a parent folder containing multiple volumes in their own folders, add "--parent" before the type.

Bonus: Since this script is using mokuro, you'll also generate a .mokuro and .html file for each volume, allowing you to read the manga with selectable text in your browser. For more info, visit the mokuro github page linked at the bottom.


# Notices

If you run into errors, look into the mokuro repository linked at the bottom. There might be some issues with python version compatibility.

Also important: This script is not perfect. The text recognition can make mistakes and some of the extracted vocab can be wrong. If this proves to be a big issue I will look for a different method to parse vocabulary from the text.


# TODO

* Live Output from Mokuro (it can take very long)
* Separate outputs for each volume
* More advanced dictionary lookup functionality
* Support more input formats (Games, VNs?) Please suggest any you might want!
* Support other output formats


# Acknowledgements

This is hardly my work, I just stringed together some amazing libraries:

* mokuro, to extract lines of text from manga - https://github.com/kha-white/mokuro
* mecab-python3, to tokenize japanese text and extract the dictionary forms - https://github.com/SamuraiT/mecab-python3
* unidic_lite, for data necessary for mecab to work - https://github.com/polm/unidic-lite
* jisho.org, for their API to look up words - https://jisho.org

