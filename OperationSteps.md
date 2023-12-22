## generative-models
```
cd generative-models/
python3 -m venv .pt2
source .pt2/bin/activate

PYTHONPATH=$PWD streamlit run scripts/demo/sampling.py --server.port 7860

```
- Put weights in /checkpoints/
