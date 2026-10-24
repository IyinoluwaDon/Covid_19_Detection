# COVID-19 Chest X-ray Classification Demo

A Flask interface around a saved Keras model from a historical chest-radiograph classification experiment. It applies the original 128 × 128 grayscale preprocessing and displays the model's dataset class.

## What is included

- PNG/JPEG uploads processed in memory, limited to 8 MB
- Lazy loading of the bundled model
- Regression tests for upload and preprocessing behavior

## Run locally

```sh
python -m venv .venv
# Activate .venv, then:
python -m pip install -r requirements.txt
python app/app.py
```

## Verify

python -m pip install -r requirements-dev.txt
python -m pytest -q

## Repository map

`app/` contains the Flask application and inference code, including `CovidTest.h5`. `ML_model/` contains the original notebook. `tests/` covers request and preprocessing behavior.

## Evidence and limitations

The saved model can be exercised through the inference code; automated tests use synthetic inputs and do not establish diagnostic performance. The repository has no independently reproduced evaluation report.

Historical educational demo only. Not for diagnosis, triage, treatment, isolation or other health decisions. Dataset provenance, license, class mapping and patient-separated external validation need verification. Do not upload identifiable health data to a public deployment.

## License

No repository license file is included. Unless the project owner adds a license, do not assume the code, data or model artifacts may be redistributed or reused. Verify third-party data and model terms separately.
