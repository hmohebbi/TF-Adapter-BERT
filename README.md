# TF-Adapter-BERT
A TensorFlow 2.0 implementation of Adapters in NLP as described in the paper [Parameter-Efficient Transfer Learning for NLP](https://arxiv.org/abs/1902.00751) based on [HuggingFace](https://github.com/huggingface/transformers)'s Transformers.


## Usage
An example of training adapters in BERT's encoders on the MRPC classification task:
```
pip install transformers

python run_tf_glue_adapter_bert.py \
  --casing bert-base-uncased \
  --bottleneck_size 64\
  --non_linearity gelu\
  --task mrpc \
  --batch_size 32 \
  --epochs 10 \
  --max_seq_length 128 \
  --learning_rate 3e-4 \
  --warmup_ratio 0.1 \
  --saved_models_dir "saved_models"\
  ```

## Results on [GLUE](https://gluebenchmark.com/) test sets
| CoLA  | SST-2  | MRPC  | STS-B  | QQP  | MNLI(m)  | MNLI(mm)  | QNLI  | RTE  | Total |
| ----|:----:| ----:| ----:| ----:| ----:| ----:| ----:| ----:| ----:|
| 55.2 | 90.9 | 88.7 | 82.5 | 71.4 | 84.1 | 83.3 | 90.6 | 68.2 |79.4 |
