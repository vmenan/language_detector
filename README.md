# language_detector

## Setting up enviroment
use the `requirements.txt` to install the essential packages.
the code was tested using `python==3.8.19`
you may have to install jupyter notebook seperately.


## Steps followed
We will follow a three step procedure to identify the language of the document.

 1. Convert the document (expected as pdf) to text using the `pdftotext` module. This module was fairly straight forward to install before, now it does give some trouble, but I was able install it using the instructions provided in the link [here](https://github.com/jalan/pdftotext).
 2. We shall remove all the empty new lines and then split the text in using the following regular expression `\w+|[^\w\s]+` this is one of the simplest pretokenizers used by HuggingFace, which splits in whitespaces.
 3. Identify the majority language in the token using the `fasttext` model released by the [NLLB team](https://github.com/facebookresearch/fairseq/tree/nllb?tab=readme-ov-file). You can download the 1GB model using this link [here](https://tinyurl.com/nllblid218e).

Finally we report what the majority language was and its percentage.

## General Note
All the code is contained inside `language_detector.ipynb` notebook. This method is not fool proof, it can be still be improved and optimized. 
Place the model downloaded in step 2 above, into a folder called `model/`
All input pdfs should be placed inside `data/`. A sample pdf is provided.


