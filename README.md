# Nougat Replication

This is the entire codebase for replicating the results from [the Nougat paper by Meta](https://arxiv.org/abs/2308.13418). It includes all necessary parts from downloading the dataset to running the final evaluation on a newly-built testing data packet (run through Nougat data pre-processing pipeline). To make it run, I include all necessary dependencies and make a few fixes to the original codebase (so I include some "duplicate" files in this codebase because they contain fixes).

This repository includes the following contents that are not part of the original paper and should obey its original open-source licensing:

* `PDFFigures2.jar` - from [PDFFigures2](https://github.com/allenai/pdffigures2).
* `test.py` - from [Nougat](https://github.com/facebookresearch/nougat).
* `index_builder.py` - from [Nougat](https://github.com/facebookresearch/nougat).
* `lightning_module.py` - from [Nougat](https://github.com/facebookresearch/nougat).

You only need `PDFFigures2.jar` when mentioned in the corresponding notebook. You will find that out ;)

## Notebooks

The notebooks are organized in the order of their executions. The notebook 0 to 3 should be run on a CPU machine, while the notebook 4 should be run on a GPU machine.

**NOTE:** The notebook 4 is designed to be run on Google Colab, thus it includes some specific code for mounting Google Drive and installing the necessary dependencies. You can also run it on a local machine, but you need to install the dependencies manually and change the working dir path used in the notebook.

## Environment

### Notebook 0-3: `environment.yml`

The `environment.yml` file is for creating a conda environment used in pre-processing your downloaded arXiv datasets (from downloading to building the seek map, which corresponds to notebooks from 0 to 3). This is made seperated because it can be run on a CPU machine for saving GPU resources.

### Notebook 4: included in the notebook

To evaluate the dataset on a GPU machine (which actually runs the Nougat model, corresponding to notebook 4), you probably only need the following package:

```bash
pip install "nougat-ocr[dataset]"
```

**Note:** You don't necessarily need to install it in your GPU machine via terminal. The notebook includes necessary installation commands for you!

## Reference to the original Nougat paper

```
@misc{blecher2023nougat,
      title={Nougat: Neural Optical Understanding for Academic Documents}, 
      author={Lukas Blecher and Guillem Cucurull and Thomas Scialom and Robert Stojnic},
      year={2023},
      eprint={2308.13418},
      archivePrefix={arXiv},
      primaryClass={cs.LG}
}
```
