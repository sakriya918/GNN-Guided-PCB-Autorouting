# GNN-Guided-PCB-Autorouting

A hybrid autorouter that teaches a graph neural network *where to start*, then lets A* do the careful work: PCB layouts are encoded as graphs, GCN/GAT models predict routing priorities, and A* routes the board while strictly enforcing design rules.

**Status: working end-to-end pipeline, validated on synthetic PCB data**

## Highlights
PCB layouts are graph-encoded so the model can reason about how components and connections relate, and GCN and GAT models use that structure to predict which connections should be routed first. A* then performs the routing itself and strictly enforces DRC and obstacle constraints, so learning proposes and constraints decide. The pipeline runs end to end, from data acquisition through to generalisation, and has been validated on synthetic PCB data. The next step is to apply it to a hand-designed LNA circuit to test whether GNN-guided routing can improve an existing hand-routed PCB.

## Tech Stack
GCN · GAT · A* search

## Pipeline
Graph-encoded PCB layout → GCN/GAT → routing priorities → A* with DRC/obstacle constraints → routed board
