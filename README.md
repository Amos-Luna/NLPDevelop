# Enhance OCR lecture

This project involves getting the best candidate word to replace the anomaly and incongruent word extracted with OCR.

We'll use pre-trained model `Bidirectional Encoder Representations from Transformers - BERT` to get the best word candidate that replace the incorrect word.

## Requirements
   ```
    $ python --version
    Python 3.10.9
  ```
## Development
Follow the instructions:

* Clone the repository on your local machine
```
    git clone https://github.com/Amos-Luna/Enhancer_OCR_NLP.git
    cd Enhancer_OCR_NLP
```

* Create your custom virtual environment -> example: `nlp_venv`
```
    py -m venv nlp_venv
    source nlp_venv/Scripts/activate
```

* Install dependencies and open VSCode
```
    pip install -r requirements.txt
    code .
```

# Image with anomalies in text

* Image with defects and distortion in text visualization

   ![local image](https://raw.githubusercontent.com/Amos-Luna/Enhancer_OCR_NLP/main/test_image.png?token=GHSAT0AAAAAAB6CI44AGWO6NEYP5NCFE6ZIY7AEU6Q)

* Extracted text after image processing and applying pytesseract-ocr techniques:
```
    Now we are creating an OCR for handwritten
    Bengali text. The main problem arises due to
    the fact that we are doing it for handwritten
    text. So our sample set is very infinite. Also
    different samples have different
    charac@@ristics. The handwriting samples are
    collected from different persons, hence it is
    very unlf~ly that they will follow a similar
    pattern.
```
   ---- Evidently, we get incorrect words: [**charac@@ristics** , **unlf~ly**]

* Mask incorrect words with the string `[MASK]`:
```
    Now we are creating an OCR for handwritten
    Bengali text. The main problem arises due to
    the fact that we are doing it for handwritten
    text. So our sample set is very infinite. Also
    different samples have different
    [MASK]. The handwriting samples are
    collected from different persons, hence it is
    very [MASK] that they will follow a similar
    pattern.
```

* Applying BERT-transformers to find the best candidate word, we obtain the correct sentence:
```
    Now we are creating an OCR for handwritten
    Bengali text. The main problem arises due to
    the fact that we are doing it for handwritten
    text. So our sample set is very infinite. Also
    different samples have different
    characteristics. The handwriting samples are
    collected from different persons, hence it is
    very unlikely that they will follow a similar
    pattern.
```
   ---- Evidently, it has the correct word involved in context of the sentence: [**characteristics** , **unlikely**]
