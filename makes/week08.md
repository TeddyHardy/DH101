---
layout: page
title: "Make 7: Networks of Knowledge and Power"
---

<p class="make-meta">Networks of Knowledge & Power</p>

## Network Visualization: AI Supply Chain Network

I mapped the AI supply chain from the mines where raw materials are dug up to the data centers where AI models are trained. The network has **23 nodes** (extraction sites, workers, mining companies, battery and materials makers, chip companies, AI companies, and data centers) and **24 connections** across **7 relationship types**.

![Network graph of the AI supply chain. On the left, cobalt mines in the DRC, lithium brine in Chile, and quartz in Spruce Pine, North Carolina, connect to mining companies and to artisanal cobalt miners. In the middle, battery makers (Huayou Cobalt, LG Energy Solution, CATL, Tesla) and chip companies (ASML, TSMC, SK Hynix, Foxconn, NVIDIA) pass materials along. On the right, Microsoft, OpenAI, and xAI connect to data centers in West Des Moines, Iowa and Memphis, Tennessee. NVIDIA sits at the center of the chip side with the most connections.]({{ site.baseurl }}/assets/images/week08/network.png)

[Explore the interactive version of my AI supply chain network on Kumu](https://kumu.io/thardy/networks-of-knowledge-and-power)

**How to read it:** node colors and shapes show the type of actor, and line colors and styles show the type of relationship. Red marks the workers at the start of the chain, brown dashed lines show extraction, gray lines show materials being supplied, and blue lines show manufacturing.

<details markdown="1">
<summary>Full list of connections (text version of the network)</summary>

| From | Relationship | To |
|---|---|---|
| Artisanal cobalt miners (DRC) | works in | Cobalt mines (Kolwezi, DRC) |
| Glencore | extracts from | Cobalt mines (Kolwezi, DRC) |
| CMOC | extracts from | Cobalt mines (Kolwezi, DRC) |
| SQM | extracts from | Lithium brine (Salar de Atacama, Chile) |
| Sibelco | extracts from | High-purity quartz (Spruce Pine, NC) |
| Cobalt mines (Kolwezi, DRC) | supplies to | Huayou Cobalt |
| Huayou Cobalt | supplies to | LG Energy Solution |
| SQM | supplies to | LG Energy Solution |
| LG Energy Solution | supplies to | Tesla |
| CATL | supplies to | Tesla |
| CATL | invests in | CMOC |
| Tesla | supplies to | xAI Colossus (Memphis, TN) |
| High-purity quartz (Spruce Pine, NC) | supplies to | Silicon wafer makers (e.g. Shin-Etsu) |
| Silicon wafer makers (e.g. Shin-Etsu) | supplies to | TSMC |
| ASML | supplies to | TSMC |
| TSMC | manufactures for | NVIDIA |
| SK Hynix | supplies to | NVIDIA |
| Foxconn | manufactures for | NVIDIA |
| NVIDIA | supplies to | Microsoft |
| NVIDIA | supplies to | xAI |
| Microsoft | invests in | OpenAI |
| Microsoft | operates | Microsoft data centers (West Des Moines, IA) |
| xAI | operates | xAI Colossus (Memphis, TN) |
| OpenAI | trains models in | Microsoft data centers (West Des Moines, IA) |

</details>

## Network Analysis

The most central node in my network is NVIDIA. It has the most connections (five) and the highest betweenness centrality, meaning it is the main bridge between the companies that make chip parts and the companies that use AI. TSMC manufactures NVIDIA's chips, SK Hynix supplies its memory, Foxconn assembles its servers, and Microsoft and xAI buy its GPUs. Almost every path from raw materials to AI models has to pass through NVIDIA, which shows how much power one chip designer has over the entire industry.

Two clusters emerged. The first is a battery and energy cluster: cobalt from the DRC and lithium from Chile flow through refiners like Huayou Cobalt and battery makers like LG Energy Solution and CATL to Tesla, whose Megapack batteries power xAI's Colossus data center in Memphis. The second is a chip cluster: quartz from Spruce Pine, North Carolina becomes silicon wafers, which TSMC turns into NVIDIA chips using ASML's machines. These two clusters only meet at the very end, at the AI companies and their data centers.

What surprised me most was how many links depend on a single place or company. Almost all high-purity quartz for chipmaking comes from one small town in North Carolina, and ASML is the only company that makes the most advanced chipmaking machines. If either one stopped, the whole chip side of the network would be disrupted.

What is missing from this network is just as important. Artisanal miners appear only on the edge, with a single connection, even though their labor starts the entire chain. The network also leaves out factory workers at Foxconn, data labelers, the water and electricity data centers use, the communities living next to mines and data centers, and the e-waste created when hardware is thrown away. A supply chain map shows how products move, but it mostly hides the people and environments that pay the costs.

## Artist Statement

My network shows that power in the AI supply chain is concentrated in a few companies in the middle and at the end of the chain. NVIDIA, TSMC, Microsoft, and OpenAI sit at the center because everything flows toward them. They decide what gets built, which suppliers they buy from, and where data centers go. The farther a node is from those companies, the less power it has.

The most visible actors are the large corporations whose names most people already know. They are well documented because they publish earnings reports, sign supply deals, and appear in the news. The invisible actors are the people at the beginning of the chain. Artisanal cobalt miners in the DRC, including children, dig the materials that make batteries possible, yet in my network they have only one connection and sit on the edge. Communities like Boxtown in Memphis, who live next to the gas turbines powering xAI's data center, are only visible as a location label.

A different network structure would tell a different story. If I had organized the network by country, it would show how resources flow from the Global South to companies in the United States, Taiwan, and China. If I had weighted the edges by money, the corporations would look even more powerful. If I had weighted them by environmental or human cost, the mines and data center communities would become the largest nodes. Every network is a choice about what to measure, and my choice shows that the people who do the most dangerous work are often the least visible.

## Attribution & AI Use

- **Tools:** Kumu (interactive network), Python/matplotlib (static image of the same data)
- **Sources:** Amnesty International, *This Is What We Die For* (2016); AP reporting on Microsoft's Iowa data centers (2023); Data Center Dynamics on xAI's Tesla Megapacks (2025); SQM and LG Energy Solution supply agreement (2023); reporting on Spruce Pine high-purity quartz (2024)
- **AI help:** Claude helped me research the supply chain connections, build the network data and visualization, and draft my analysis and artist statement, which I reviewed and revised.

[← Back to all makes]({{ site.baseurl }}/)
