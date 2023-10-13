# Pre-Activation Feature Extraction based Transfer Learning

This repository contains the code for performing pre-activation feature extraction based transfer learning to predict materials properties using elemental fractions (EF), physical attributes (PA), or extracted features as the model input. The code provides the following functions:

* Train an ElemNet model on a given dataset.
* Use a pre-trained ElemNet model to perform transfer learning on a given target dataset.
* Predict material properties of new compounds with a pre-trained ElemNet model.

It is recommended to train large dataset (e.g. OQMD, MP) from scratch (SC) and small datasets (DFT-computed or experimental datasets) using transfer learning methods.

## Installation Requirements

The basic requirement for using the files is a Python 3.6.3 environment with the packages listed in `requirements.txt`. It is advisable to create a virtual environment with the correct dependencies.

The work related experiments were performed on Linux Fedora 7.9 Maipo. The code should be able to work on other Operating Systems as well, but it has not been tested elsewhere.

## Source Files
  
Here is a brief description of the files and folder content:

* [`log`](./log): folder where the output log from the training will be saved.

* [`model`](./model): folder where trained model will be saved.

* [`sample`](./sample): folder where the config file is stored.

* `dl_regressors_tf2.py`: code to run the ElemNet model.

* `pre-activation representation.ipynb`: Jupyter Notebook to perform feature extraction from a specific layer of pre-trained ElemNet model.

* `data_preprocess.ipynb`: Jupyter Notebook to convert the chemical formula of a compound into elemental fractions and physical attributes.

* `test_prediction.ipynb`: Jupyter Notebook to perform prediction using the pre-trained ElemNet model.

## Running the code

The code to run the ElemNet model is provided in the network folder. In order to run the model, you can pass a sample config file to the dl_regressors_tf2.py from inside of your network directory:

`python dl_regressors_tf2.py --config_file sample/sample-run_example_tf2.config`

The config file defines all the related hyperparameters associated with the model training and model testing, such as loss_type, training_data_path, val_data_path, test_data_path, label, input_type, etc. To add customized input_type, please make changes to the `data_utils.py`.

## Developer Team

The code was developed by Vishu Gupta from the <a href="http://cucis.ece.northwestern.edu/">CUCIS</a> group at the Electrical and Computer Engineering Department at Northwestern University.

## Publication

1. Vishu Gupta, Wei-keng Liao, Alok Choudhary, and Ankit Agrawal. "Pre-activation based representation learning to enhance predictive analytics on small materials data." In 2023 International Joint Conference on Neural Networks (IJCNN), pp. 1-8. IEEE, 2023. [<a href="https://ieeexplore.ieee.org/abstract/document/10191086">DOI</a>] [<a href="https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=10191086">PDF</a>]

```tex
@inproceedings{gupta2023pre,
  title={Pre-activation based representation learning to enhance predictive analytics on small materials data},
  author={Gupta, Vishu and Liao, Wei-keng and Choudhary, Alok and Agrawal, Ankit},
  booktitle={2023 International Joint Conference on Neural Networks (IJCNN)},
  pages={1--8},
  year={2023},
  organization={IEEE}
}
```

## Acknowledgements

The open-source implementation of ElemNet <a href="https://github.com/NU-CUCIS/ElemNet">here</a> provided significant initial inspiration for the structure of this code-base.

## Disclaimer

The research code shared in this repository is shared without any support or guarantee on its quality. However, please do raise an issue if you find anything wrong and I will try my best to address it.

email: vishugupta2020@u.northwestern.edu

Copyright (C) 2021, Northwestern University.

See COPYRIGHT notice in top-level directory.

## Funding Support

This work was performed under the following financial assistance award 70NANB19H005 from U.S. Department of Commerce, National Institute of Standards and Technology as part of the Center for Hierarchical Materials Design (CHiMaD). Partial support is also acknowledged from Department of Energy (DOE) awards DE-SC0019358, DE-SC0021399, and NSF award CMMI-2053929, and Northwestern Center for Nanocombinatorics.
