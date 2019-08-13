<h1 align="center"> Workshop and tutorial materials for solaris </h1>
<p align="center">
<img src="https://github.com/CosmiQ/solaris_tutorials/blob/master/solaris_powered_by.png" width="350" alt="Powered by Solaris">
</p>

This repo contains materials from CosmiQ Works' open source and/or public workshops on using `solaris` for geospatial ML applications. Each sub-directory corresponds to a specific workshop or tutorial. Some of the workshop materials will require additional data download and/or preparation beyond the contents of the repository; see the README files within each workshop for additional instructions.

Note that many of the workshops may require access to (at times substantial) GPU resources for model training. We've tried to indicate that both in the outline below as well as within the workshop materials themselves.

## Workshop list and topics

### [FOSS4G 2019 Workshop on Solaris](https://github.com/CosmiQ/solaris_tutorials/tree/master/Solaris_FOSS4G_2019)

#### Requirements:

Familiarity with Python, Jupyter Notebooks, and basic concepts around geospatial data (what satellite imagery is, what vector-formatted labels are). Solaris must already be [installed](https://solaris.readthedocs.io/en/latest/installation.html) on your computer. One of the notebooks requires GPU compute (to complete in any reasonable amount of time).

#### Topics:

- An intro to neural nets and machine learning for geospatial applications (_slides_)
- Running inference with a pre-trained model from a SpaceNet Challenge (_Jupyter Notebooks_)
- Evaluating model performance (_slides and Jupyter Notebook_)
- Fine-tuning a pre-trained model on new imagery (_Jupyter Notebook_) ___requires GPU resources___
- Multi-channel training targets and combination loss functions (_slides and Jupyter Notebook_)
