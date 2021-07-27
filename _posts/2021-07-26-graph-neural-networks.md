---
layout: post
title: Graph Neural Networks
date: 2021-07-26 12:00:00
description: Tracking my progress towards learning GNNs for my research internship at IIT Patna
---
##### Video lectures - [YouTube playlist: CS224W](https://www.youtube.com/playlist?list=PLoROMvodv4rPLKxIpqhjhPgdQy7imNkDn)
##### Textbook - [Graph Representation Learning - William A. Hamilton](cs.mcgill.ca/~wlh/grl_book/)
##### Course - [CS224W](https://cs224w.stanford.edu/)
------------

## Day 1 (26th July)

- What are graphs?
- Machine learning tasks on graphs
    - Node classification
    - Link (Relation) prediction
    - ...
- Node-level features
    - Node Degree
    - Node Centrality
        - Eigenvector Centrality [a node is important if its neighbors are important] (*have to re-read - linear algebra concepts*)
        - Betweenness Centrality [a node is important if it is an important connector/bridge]
        - Closeness Centrality [a node is important if it is close to many nodes]
    - Clustering Coefficient (local structure) [a node is important if its neighboring nodes are highly connected with each other]
    - Graphlets (!)
        - Observation: Clustering coefficent = no. of triangles in the ego network of a nodes
        - Generalize this notion by counting occurrences of different graphlets
        - Graphlet Degree Vector (different from Graphlet Features - from graphlet kernel)
- Link-level features (*yet to read*)
- Graph-level features
    - Kernel methods (*have to understand fundamentals of kernels*)
        - Graphlet kernel [Bag-of-Words for a graph]
        - Weisfeiler-Lehman kernel [Bag-of-Colors/Generalized version of Bag-of-Words]
            - Isomorphism Test
- Node Embeddings
    - Task: map nodes into an embedding space
    - Properties of embeddings
        - Unsupervised/self-supervised learning (node labels/features are not utilized)
        - Task-independent
    - "Shallow" Encoding
        - Process
            1. Encoder - nodes 🡒 embeddings [encoder = embedding lookup]
            2. Node similarity function (in original network)
            3. Decoder - embeddings 🡒 similarity score (for the embeddings) [usually just the dot product]
            4. Optimize encoder parameters (node embeddings) such that $$ similarity(u, v) \approx z_u^Tz_v $$
        - How to define node similarity?
            - [DeepWalk, node2vec](https://www.youtube.com/watch?v=Xv0wRy66Big)
        - Link between Matrix Factorization and Node Embeddings - [Network Embedding as Matrix Factorization: Unifying DeepWalk, LINE, PTE, and node2vec](https://arxiv.org/abs/1710.02971)
        - Limitations (matrix factorization, random walks)
            - Cannot obtain embeddings for nodes not in the training set (all embeddings need to be recomputed - random walks)
            - Cannot capture structural similarity (solved by anonymous walks - *yet to read*)
            - Cannot utilize node, link, graph features