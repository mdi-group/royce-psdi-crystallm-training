# CrystaLLM-pi Workshop - PSDI & Royce Materials Data Summit 

### How to use CrystaLLM-pi to predict crystal structures with desired functional properties, or match experimental data and adapt the model to your own data

In this tutorial, we will cover how the user can load up and make predictions with pre-packaged deep learning models to generate material structures with a target property or matching measured experimental data signals on their own devices. Additionally, we will show how to format your own data in order to adapt the model so it can make structure predictions conditioned on a desired property.

### Learning outcomes
- Increased understanding of the inside workings of a specialised transformer model that can generate crystal structures conditioned on functional properties
- Gain the skills to load pre-trained models and generate materials with desired attributes on your own device
- Understand how to format structure and property data so it can be used for training a transformer
- Learn how to adapt a toy model to this dataset to understand how it could be applied to your data

### Tutorial outline
The current course materials are organised around three main practical themes:

- [Introduction to deep learning](./slides/intro_to_deep_learning.pptx) covering representations and embeddings, leading to sequence-to-sequence modelling for natural language and Crystallographic Information Files (CIFs) and the importance of memory and context.
- [Attention, transformers and CrystaLLM](./slides/intro_to_transformer_crystallm.pptx) covering the attention mechanism, token embeddings, attention weights, and how attention leads naturally into transformer-style models, leading to CrystaLLM 
- [CrystaLLM-pi property conditioning](./slides/CrystaLLM-pi-property-conditioning.pptx) covering how to fine-tune pretrained CrystaLLM models and use attention conditioning mechanisms to steer CrystaLLM-pi (property injection) crystal generation towards desired properties.

### Hands-on notebooks

- [![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/mdi-group/royce-psdi-crystallm-training/blob/master/notebooks/load_and_generate_colab.ipynb) [load_and_generate.ipynb](./notebooks/load_and_generate_colab.ipynb) introduces how to load a CrystaLLM model from HuggingFace and use it to generate crystal structures
- [![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/mdi-group/royce-psdi-crystallm-training/blob/master/notebooks/Z_finetune_density_example_colab.ipynb) [Z_finetune_density_example.ipynb](./notebooks/Z_finetune_density_example_colab.ipynb) demonstrates how to load a pretrained CrystaLLM-pi model and finetune it on additional CIF data, how to prepare your data for fine-tuning, and how to condition generation towards specific functional properties

## Further Resources

- [CrystaLLM-pi repo](https://github.com/C-Bone-UCL/CrystaLLM-pi) source code repository of the CrystaLLM-pi
- [PSDI CrystaLLM-pi Web App](https://crystallm-pi.psdi.ac.uk/) web app to run CrystaLLM-pi in your browser!
- [PSDI CrystaLLM-pi Docker container](https://resources.psdi.ac.uk/tool/d2f426b2-04df-4ed1-8778-c2082852088c) containerised version of CrystaLLM-pi for larger jobs

## Citation

Please refer to the following when citing our work!
["Discovery and recovery of crystalline materials with property-conditioned transformers"](https://arxiv.org/pdf/2511.21299)

```
@misc{bone2025discoveryrecoverycrystallinematerials,
      title={Discovery and recovery of crystalline materials with property-conditioned transformers}, 
      author={Cyprien Bone and Matthew Walker and Kuangdai Leng and Luis M. Antunes and Ricardo Grau-Crespo and Amil Aligayev and Javier Dominguez and Keith T. Butler},
      year={2025},
      eprint={2511.21299},
      archivePrefix={arXiv},
      primaryClass={cond-mat.mtrl-sci},
      url={https://arxiv.org/abs/2511.21299}, 
}
```

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Acknowledgments
This work has been supported by UKRI funding (EP/Y000552/1 and EP/Y014405/1) and PSDI funding.
