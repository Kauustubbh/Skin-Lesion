# Skin Lesion Classifier

Semester ML/DL project — dermoscopic skin lesion classification on the HAM10000
dataset (7 diagnostic classes, ~10,015 images, class-imbalanced) using transfer
learning (ResNet50/MobileNet), served through a Flask app.

Mentor: Prof. Amandeep Kaur. Full scope, timeline and stretch-goal breakdown:
see `project-plan.html`. CNN/transfer-learning concepts already covered: see
`concepts-learned.md`.

## Team & roles

| Person | Owns |
|---|---|
| TBD | Data pipeline — acquisition, EDA, lesion_id-safe split, augmentation |
| TBD | Model & training — transfer learning setup, training loop, class imbalance |
| TBD | Evaluation & analysis — metrics, confusion matrix, error analysis |
| TBD | Flask + Docker — inference API, containerization |

## Folder structure

```
data/         raw HAM10000 images + metadata (gitignored — pulled fresh via
              Kaggle API each Colab session, not committed)
notebooks/    Colab/Jupyter notebooks — EDA, training, evaluation
src/          clean .py scripts pulled out of notebooks once stable
              (this is what flask_app/ imports from)
flask_app/    the Flask inference app
models/       trained model weight files (gitignored — share via a team
              Google Drive folder, not git, they're too large)
```

## Getting the dataset

Each person needs their own Kaggle API token (kaggle.com -> Account ->
Create New Token, downloads `kaggle.json`). In Colab:

```python
!pip install kaggle
# upload kaggle.json when prompted (or read it from Google Drive)
!kaggle datasets download -d kmader/skin-cancer-mnist-ham10000
!unzip -q skin-cancer-mnist-ham10000.zip -d data/
```

## Status

- [ ] Repo scaffolded
- [ ] Roles assigned
- [ ] Dataset EDA
- [ ] Train/val/test split (by lesion_id, not image)
- [ ] Architecture picked (ResNet50 / MobileNet / EfficientNet)
- [ ] Baseline trained
- [ ] Flask skeleton
- [ ] Real evaluation (confusion matrix, per-class precision/recall/F1)
- [ ] Model swapped into Flask
- [ ] Docker
- [ ] Report
