# feature-selection-layer-tf-keras
A feature selection layer for tensorflow.keras

Created by Oliver Koch.
# Feature Selection Layer for tensorflow.keras

```
import tensorflow as tf
class FeatureSelectionLayer(tf.keras.layers.Layer):
    """ 
    A Layer that creates a one-to-one connection between the input neurons and the output neurons.
    The weights are trainable, so the layer can be used as a feature selection layer.
    
    Possible usage: e.g. gene expression data
    """  
    def __init__(self, *args, **kwargs):
        super().__init__(*args, **kwargs)
    
    def build(self, input_shape):
        self.kernel = self.add_weight("kernel", shape=(int(input_shape[-1]),))
    
    def call(self, inputs):
        return tf.multiply(inputs, self.kernel)
```

## Example Installation:
For the usage of the example jupyter-notebook, feature_selection_layer.ipynb.
Used parts of the following data: https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE158699. 

Used version of python: ```Python 3.9.5```   

1. Install miniconda (https://docs.conda.io/en/latest/miniconda.html#installing)
2. Create conda environment: ```conda create -n layer_env  python=3.9.5```
3. Activate Conda environment: ```conda activate layer_env ```
4. ```conda install ipykernel```
5. ```python -m ipykernel install --name layer_env --user```
6. ```conda install -c conda-forge jupyterlab```


Please install te following packages, to use the FeatureLayer.
Used Packages:
```conda install -c conda-forge tensorflow```
```conda install pandas```

# Start jupyter-lab
jupyter-lab

