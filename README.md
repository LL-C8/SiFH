## Setup Environment

1\. Clone this repository:

```
git clone git@github.com:LL-C8/SiFH.git
cd SiFH
```

2\. Setup conda environment:

```
conda create -n SiFH python=3.8
conda activate SiFH
sh ./scripts/setup.sh
```

3\. Setup [Argoverse 2 Motion Forecasting Dataset](https://argoverse.github.io/user-guide/datasets/motion_forecasting.html#download), the expected data structure should be:

```
wget https://s3.amazonaws.com/argoverse/datasets/av2/tars/motion-forecasting/val.tar
tar -zxvf val.tar.gz
```

## Preprocess

```
python3 preprocess --data_root=/path/to/data_root -p
```

or you can disable parallel preprocessing by removing `-p`.

## Evaluation

```
python3 eval.py data_root=/path/to/data_root batch_size=64 'checkpoint="/path/to/checkpoint"'
```
