# ShuttleNet: Position-aware Rally Progress and Player Styles Fusion for Stroke Forecasting in Badminton (AAAI 2022)
Official code of the paper **ShuttleNet: Position-aware Rally Progress and Player Styles Fusion for Stroke Forecasting in Badminton**.
Paper: https://arxiv.org/abs/2112.01044

## Overview
ShuttleNet contains two encoder-decoder modified Transformer as extractors, and a position-aware gated fusion network for fusing these contexts to tackle stroke forecasting in badminton.

## Setup
- Build environment
    ```
    conda env create -f environment.yml
    ```
- Put data in `data/dataset.csv`

## Run script
- To run all the cases, run the script `script_all.sh`:
    ```
    ./script_all.sh {model_type} {sample_num}
    ```
- To run the case with different seeds, run the script `script_seed.sh`:
    ```
    ./script_all.sh {model_type} {encode_length} {sample_num}
    ```
- To run the case with the specific seed and default samples, run the script `script_single.sh`:
    ```
    ./script_single.sh {model_type} {encode_length} {seed_value}
    ```
- You may need to modify model_type in `train.py` choices.

## Output files
- Trained models will be saved in the folder `model/{datetime}_{model_type}/`
    - Details of performance will also be contained in folder named `result.log`
- The performance will be saved in corresponding log file named {model_type}\_result\_{encode_length}

## Code structure
### Training
```=python
python train.py {model_type}
```

### Evaluate
```=python
python evaluate.py {model_path}
```

### Generate
```=python
python generator.py {model_path}
```

