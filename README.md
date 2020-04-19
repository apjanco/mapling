<h1><img src="https://image.flaticon.com/icons/png/512/40/40054.png" width="120px"><br>mapling</h1>

Mapling finds things, such as place names, in text.  It returns a csv file with a row for each occurence. For each file, it creates an html page with the things highlighted.

Usage: `$ python mapling.py texts/  --gazetteer=gazetteer/gazetteer.txt --model=de_core_news_sm --html`
To install a [spaCy model](https://spacy.io/models): `$ python -m spacy download de_core_news_sm`

- The first approach is to use a gazetteer. Mapling expects a txt file with a row for each place name.
Add the `--gazetter` argument with the path to your file. This approach lets you search for specific terms (not just places) that appear in the text.
`$ python mapling.py /dir/with/txt_files --gazetteer="/home/me/gazetter.txt"`

- The second approach uses a spaCy named entity recognition model.  Add the `--model` argument with
the name of an installed spaCy model.  If your model is not installed or does not
have an ner pipeline, you'll get instructions on how to fix that. This approach will return a large range of entities and places, more than you might list yourself.  This is useful for establishing which places, people and organizations appear in a text.
`$ python mapling.py /dir/with/txt_files  --model=de_core_news_md`


- Finally, mapling can create visualizations.  Add the `--html` argument
`$ python mapling.py /dir/with/txt_files  --model=de_core_news_md --html`

To install:
```
(myenv) $ git clone https://github.com/apjanco/mapling.git
(myenv) $ cd mapling
(myenv) $ pip install -r requirements.txt
```


Output is a csv file:
#TODO example table
#TODO use of the file in Historical Gazetteer
