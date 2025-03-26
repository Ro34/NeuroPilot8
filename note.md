# 1. installation
## system requirements
```bash
Python 3.5 to Python 3.11
pip>=8.1.0
```

## python dependencies
### Required:
```bash
argparse >= 1.2
flatbuffers >= 1.12.0
jsonschema
lxml
matplotlib >= 3.2
natsort
networkx
numpy >= 1.13.3
packaging
plotly
protobuf >= 3.5.1 and < 4.0
pybind11 >= 2.2
singleton-decorator
tqdm >= 4.0
xxhash
```
### Optional:
```bash
tensorflow version: >= 1.13 and < 2.16 (required by TensorFlow V1 Converter)

tensorflow version: >= 2.0 and < 2.16 (required by TensorFlow Converter)

torch version: >= 1.3 and < 2.6 (required by PyTorch Converter and the PyTorch Delegator)

torch version: >= 2.1 and < 2.6 (required by PyTorch V2 Converter)

onnx version: >= 1.3 and < 1.14 (required by ONNX Converter)
```
### Note:

Converter Tool is well tested with the following versions of TensorFlow: 1.13, 1.14, 1.15, 2.2, 2.6, 2.11, 2.13, 2.15.

## Tool installation
### Converter Tool
```bash
unzip mtk_converter-<version>+packages.zip
# For Python 3.10
pip3 install mtk_converter-<version>+release-cp310-cp310-manylinux_2_17_x86_64.manylinux2014_x86_64.whl
```
### Quantization Tool
```bash
pip3 install mtk_quantization-<version>-py3-none-any.whl
```

## Model Preparation
### Preparing Model Weights
```bash
mkdir GAI-Deployment-Toolkit-<toolkit_version>_<model_name>-<model_version>/models/<model_name>/

#GAI-Deployment-Toolkit-<toolkit_version>_<model_name>-<model_version>/
# └ models/
#   └ <model_name>/
#     ├ pytorch_model-00001-of-00002.bin (or model-00001-or-0000x.safetensors)
#     ├ pytorch_model-00002-of-00002.bin (or model-00002-or-0000x.safetensors)
#     ├ config.json
#     ├ tokenizer_config.json
#     ├ special_tokens_map.json
#     └ tokenizer.model (or tokenizer.json)
```
# 2.Conversion and PTQ
## prepare model for PTQ
```bash
cd GAI-Deployment-Toolkit-<toolkit_version>_<model_name>-<model_version>/post_training_quantize
bash 1_make_ptq_calibration_dataset.sh

```
## Performing PTQ on the Model
```bash
bash 2_ptq.sh
```

