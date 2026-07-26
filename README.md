# WC2026 Final: Pass Network Analysis
## Spain vs Argentina | July 19, 2026

This project performs a comparative Social Network Analysis of the pass
networks from the 2026 FIFA World Cup final between Spain and Argentina.
It builds directed weighted graphs from raw match event data, where nodes
are players and edges represent completed passes, then compares both teams
using centrality measures, temporal phase analysis, community detection,
and directed triangle detection. Structurally, [INSERT KEY FINDING].

## Project Structure

```
PROJECT_2/
├── data/
│   ├── raw/          # Original match event CSV
│   └── clean/        # Processed edgelist files (10 files)
├── notebooks/
│   ├── 01_graph_construction.ipynb   # Builds graphs from CSV
│   └── 02_analysis.ipynb             # Full SNA analysis
├── pics/             # All visualizations (combined and split)
└── README.md
```

## Dataset

The source data is the WC2026 final event data for Spain versus Argentina,
played on July 19, 2026, covering every touch, pass, and match event with
pitch coordinates and timestamps. Argentina received a red card at
expandedMinute 97, Enzo Fernandez, double yellow, and played with 10 men
through the rest of the second half and the entirety of extra time, which
is the basis for the temporal phase comparison in this analysis.

## How to Reproduce

1. Clone the repository
2. Install dependencies: networkx, pandas, numpy, matplotlib, seaborn,
   community (python-louvain), powerlaw

   ```
   pip install networkx pandas numpy matplotlib seaborn python-louvain powerlaw
   ```
3. Run 01_graph_construction.ipynb from the notebooks/ folder
4. Run 02_analysis.ipynb from the notebooks/ folder
5. All outputs (edgelists and plots) are saved automatically to
   data/clean/ and pics/

## Analysis Sections

A brief description of each analysis section in 02_analysis.ipynb.

- Introduction: network classification and pitch visualization
- Network Characteristics: density, clustering, distance metrics
- Centrality Measures: degree, betweenness, eigenvector, PageRank
- Degree Distribution: weighted pass volume per player
- Temporal Analysis: how networks evolved across match phases
- Community Detection: Louvain communities and triangle detection

## Key Visualizations

| File | What it shows |
| --- | --- |
| pitch_visualization.png | Full match pass network for both teams on a pitch background |
| centrality_in_degree.png | Players ranked by in degree centrality, most sought out receivers |
| centrality_out_degree.png | Players ranked by out degree centrality, most active distributors |
| centrality_betweenness.png | Players ranked by betweenness centrality, bridges in the passing network |
| centrality_eigenvector.png | Players ranked by eigenvector centrality, connections to other well connected players |
| centrality_pagerank.png | Players ranked by PageRank, weighted importance as a pass receiver |
| degree_distribution.png | Weighted in degree and out degree distribution per player |
| temporal_networks.png | Pass networks for each of the four match phases, both teams |
| communities_louvain.png | Louvain passing communities on the pitch, both teams |
| triangles.png | Top three passing triangles per team, isolated on the pitch |

## References

Social Networks Analysis, Universidad Politecnica de Yucatan.

Newman, M. (2018). Networks. Oxford University Press.

Barabasi, A. L. (2016). Network Science. Cambridge University Press.

Menczer, F., Fortunato, S., and Davis, C. A. (2020). A First Course in
Network Science. Cambridge University Press.
