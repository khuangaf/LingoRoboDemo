# LingoRobo
To view the demo website, click this [link](https://khuangaf.github.io/LingoRoboDemo/).

## CSCI 527 Applied Machine Learning for Games 

Enabling AI agents following natural language instructions is critical for games. Imagine when you are playing [Pokemon](https://www.pokemon.com/us/) games, and your [Pikachu](https://media.izi.travel/4e9d2b2c-83c3-4a84-8675-7cc276270305/fc7197c5-14e1-481e-998d-9e90b0bd2d0f_800x600.jpg) can strike thunder to its opponents when you . That would be so much fun!! Yet, the technology is not there yet. This project aims to bridge the gap between natural language instructions and agents' actions. 

## Project Owners:
* [Kung-Hsiang Steeve Huang](http://khuangaf.github.io/)*
* [Shikhar Singh](https://www.linkedin.com/in/shikhar-singh-730910a7).*

*equal contribution

## Workload Distribution:
* Kung-Hsiang Steeve Huang: knowledge incorporation, project website.
* Shikhar Singh: visual grounding, demo video.

## Task
We develop our system on the [ALFRED dataset](https://arxiv.org/abs/1912.01734) (Action Learning From Realistic Environments and Directives). ALFRED is a benchmark for challenges AI agents to a map between natural language instructions and sequences of agents.

<img src="https://github.com/khuangaf/LingoRoboDemo/raw/gh-pages/alfred.jpg" />


## Methods
We approach the ALFRED dataset in two directions:
* Commonsense knowledge incorporation (Steeve)
* Grounding between action space, visual space, and semantic space. (Shikhar)

### Commonsense knowledge incorporation
[ConceptNet](https://conceptnet.io/) is a multi-lingual open source knowledge base that contains rich common sense knowledge. To integrate knowledge into text-based model, we need to fetch the most relevant sub-graph for each instruction. First, [Spacy Matcher](https://spacy.io/api/matcher) is used for grounding mentions in instructions to concepts in ConceptNet. Pairwise relations between grounded concepts are found by running shortest path algorithm implemented by [NetworkX](https://networkx.org/documentation/stable/index.html). Tokens in instructions are linked to corresponding concepts. Following these steps, we obtain a sub-graph for each instruction. Graph Convolutional Networks (GCN) is used for updating the token embeddings on each sub-graph. We used the [PyTorch Geometric](https://pytorch-geometric.readthedocs.io/en/latest/index.html) implementation of GCN. 
<img src="https://github.com/khuangaf/LingoRoboDemo/raw/gh-pages/gcn.jpg" />

### Visual grounding


## Demo

<iframe width="560" height="315" src="https://www.youtube.com/embed/1XoRLNmXffo" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## Resources
* [EDD](https://drive.google.com/drive/folders/1qK96aHT75uXB1F_f56ti4HhiZeESCDau?usp=sharing)
* [Technical paper](https://drive.google.com/drive/folders/1qK96aHT75uXB1F_f56ti4HhiZeESCDau?usp=sharing)
