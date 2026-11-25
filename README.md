# Plutchik's Emotion Classifier

The model is trained using
[deberta_train.ipynb](/deberta_train.ipynb).
For the sake of simplicity,
we used HuggingFace's `transformer` library
to retrieve and interface with the pre-trained model
(DeBERTa-V3-base).

The file includes an unused custom optimizer
that uses the identical algorithm
as the built-in `AdamW` optimizer in `PyTorch`,
except that learning rate is adjusted on a more granular level.
For the scale of this task,
the differential learning rate did not bring much improvement,
and is hence disabled.

The [wrangling](/wrangling/) folder contains jupyter notebook files
use for data wrangling.

The [full_pipeline.ipynb](/full_pipeline.ipynb) file contains an embedded web interface for the classifier.
Since the LLM we used (Qwen3.8-27B) is not deployed locally,
OpenRouter credentials are required for use.
