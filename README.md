# COVID-19 Chest X-ray Classification

A Flask inference application for a saved convolutional neural network trained to classify chest radiographs into the experiment's COVID-19 and non-COVID-19 classes. The notebook scales pixel values to 0-1, trains a Conv2D/max-pooling feature extractor with a dense classifier, dropout, and sigmoid output using Adam and binary cross-entropy, then saves the Keras model.

`app/` contains the Flask routes, preprocessing, and `CovidTest.h5` model. `ML_model/covid.ipynb` contains the image-directory training workflow; the notebook's source data is arranged in COVID-19 and Non-COVID-19 class folders. The app converts uploaded images to grayscale, resizes to 128 x 128, and processes PNG/JPEG uploads in memory with an 8 MB request limit. The model loads on demand.

## Run locally

```sh
python -m venv .venv
# Activate .venv, then:
python -m pip install -r requirements.txt
python app/app.py
```

`tests/` covers request handling and preprocessing behavior.
