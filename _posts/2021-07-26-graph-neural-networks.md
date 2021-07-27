---
layout: post
title: Graph Neural Networks
date: 2021-07-26 12:00:00
description: Tracking my progress towards learning GNNs for my research internship at IIT Patna
---
##### Video lectures - [YouTube playlist: CS224W](https://www.youtube.com/playlist?list=PLoROMvodv4rPLKxIpqhjhPgdQy7imNkDn)
##### Textbook - [Graph Representation Learning - William A. Hamilton](cs.mcgill.ca/~wlh/grl_book/)
##### Course - [CS224W](https://cs224w.stanford.edu/)

# Day 1 (26th July)

- Video lectures: 1.1 to 3.2
- Textbook - 1.1 to 2.1, 3.1
- Concepts
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