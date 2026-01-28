Pipeline to Pipeline transcription model built off of the WhisperX library with Pyannote. Comes with Word Alignment, and Speaker Diarization (identifying who said what).

Features:
Processing: Uses a checkpoint system to save progress after each stage (Transcribe → Align → Diarize), so you dont lose too much work if there are issues, like with your device or the environment (you can change the checkpoint value, and batch number).

Workflow: Creates and manages project folders for audio inputs, checkpoints, and final transcripts.

Speaker Mapping: Dictionary to convert eg. "SPEAKER_00" into real names.


I built this on my Mac but it should run fine on other OS's. There is a caffeine function leftover for Mac, as Macs can have issues with the configurations and sometimes take longer, but this may not be necessary, especially a year later when libraries have had updates/improvements. 

This project is currently configured to run on CPU. While macOS has MPS (Metal) support, WhisperX currently provides better stability on CPU for the transcription/alignment pipeline.

Mandatory: You must have ffmpeg installed on your system: Brew install ffmpeg

Note: To bypass security blocks introduced in PyTorch 2.6+ that are not compatible with Pyannote models, this project uses a custom trusted_load patch.

Recommended Environment:

Python: 3.10

PyTorch: 2.5.1

How to Run:

Create a Main Folder on your Desktop named TranscriptionProject.

Place your audio file inside TranscriptionProject/audio_input/.

Hugging Face Token: Make sure you have generated a Hugging Face token (this is free) with access to the pyannote/speaker-diarization-3.1 model.

Structure:
audio_input/: Place your .m4a or .wav files here.

checkpoints/: Stores checkpoint.json so you can resume if the script crashes.

outputs/: Your final, speaker-labeled transcript.txt will appear here.

Package requirements below - 

Package                 Version
----------------------- -----------
aiohappyeyeballs        2.6.1
aiohttp                 3.13.3
aiosignal               1.4.0
alembic                 1.18.1
antlr4-python3-runtime  4.9.3
asteroid-filterbanks    0.4.0
async-timeout           5.0.1
attrs                   25.4.0
av                      16.1.0
certifi                 2026.1.4
cffi                    2.0.0
charset-normalizer      3.4.4
click                   8.3.1
coloredlogs             15.0.1
colorlog                6.10.1
contourpy               1.3.2
ctranslate2             4.6.3
cycler                  0.12.1
docopt                  0.6.2
einops                  0.8.2
faster-whisper          1.2.1
filelock                3.20.3
flatbuffers             25.12.19
fonttools               4.61.1
frozenlist              1.8.0
fsspec                  2026.1.0
hf-xet                  1.2.0
huggingface-hub         0.36.0
humanfriendly           10.0
HyperPyYAML             1.2.3
idna                    3.11
Jinja2                  3.1.6
joblib                  1.5.3
julius                  0.2.7
kiwisolver              1.4.9
lightning               2.6.0
lightning-utilities     0.15.2
Mako                    1.3.10
markdown-it-py          4.0.0
MarkupSafe              3.0.3
matplotlib              3.10.8
mdurl                   0.1.2
mpmath                  1.3.0
multidict               6.7.1
networkx                3.4.2
nltk                    3.9.2
numpy                   2.2.6
omegaconf               2.3.0
onnxruntime             1.23.2
optuna                  4.7.0
packaging               26.0
pandas                  2.3.3
pillow                  12.1.0
pip                     25.0.1
primePy                 1.3
propcache               0.4.1
protobuf                6.33.4
pyannote.audio          3.4.0
pyannote.core           5.0.0
pyannote.database       5.1.3
pyannote.metrics        3.2.1
pyannote.pipeline       3.0.1
pycparser               3.0
Pygments                2.19.2
pyparsing               3.3.2
python-dateutil         2.9.0.post0
pytorch-lightning       2.6.0
pytorch-metric-learning 2.9.0
pytz                    2025.2
PyYAML                  6.0.3
regex                   2026.1.15
requests                2.32.5
rich                    14.3.1
ruamel.yaml             0.18.17
ruamel.yaml.clib        0.2.15
safetensors             0.7.0
scikit-learn            1.7.2
scipy                   1.15.3
semver                  3.0.4
sentencepiece           0.2.1
setuptools              78.1.0
shellingham             1.5.4
six                     1.17.0
sortedcontainers        2.4.0
soundfile               0.13.1
speechbrain             1.0.3
SQLAlchemy              2.0.46
sympy                   1.13.1
tabulate                0.9.0
tensorboardX            2.6.4
threadpoolctl           3.6.0
tokenizers              0.22.2
tomli                   2.4.0
torch                   2.5.1
torch-audiomentations   0.12.0
torch_pitch_shift       1.2.5
torchaudio              2.5.1
torchmetrics            1.8.2
tqdm                    4.67.1
transformers            4.57.6
typer                   0.21.1
typing_extensions       4.15.0
tzdata                  2025.3
urllib3                 2.6.3
wheel                   0.45.1
whisperx                3.7.6
yarl                    1.22.0

