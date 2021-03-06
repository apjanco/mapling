<h1><img src="https://image.flaticon.com/icons/png/512/40/40054.png" width="120px"><br>mapling</h1>

Mapling finds things, such as place names, in texts.  It returns a csv file with a row for each occurence. For each file, it creates an html page with the things highlighted.  Just point mapling to a folder full of documents. Mapling uses [textract](https://textract.readthedocs.io/en/latest/) to extract text from many types of files, including csv, doc, docx, pdf, html, txt and many others.

Usage: `$ mapling texts/  --gazetteer=gazetteer/gazetteer.txt --model=de_core_news_sm --html`
To install a [spaCy model](https://spacy.io/models): `$ python -m spacy download de_core_news_sm`

- The first approach is to use a gazetteer. Mapling expects a txt file with a row for each place name.
Add the `--gazetter` argument with the path to your file. This approach lets you search for specific terms (not just places) that appear in the text.
`$ mapling /dir/with/txt_files --gazetteer="/home/me/gazetter.txt"`

- The second approach uses a spaCy named entity recognition model.  Add the `--model` argument with
the name of an installed spaCy model.  If your model is not installed or does not
have an ner pipeline, you'll get instructions on how to fix that. This approach will return a large range of entities and places, more than you might list yourself.  This is useful for establishing which places, people and organizations appear in a text.
`$ mapling /dir/with/txt_files  --model=de_core_news_md`


- Finally, mapling can create visualizations.  Add the `--html` argument
`$ mapling /dir/with/txt_files  --model=de_core_news_md --html`

To install:
```
pip install mapling
```

In the future, mapling will also work with the [Word Historical Gazetteer](http://dev.whgazetteer.org/) to rectify, geocode and map your place names.
