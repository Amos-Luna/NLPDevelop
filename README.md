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
