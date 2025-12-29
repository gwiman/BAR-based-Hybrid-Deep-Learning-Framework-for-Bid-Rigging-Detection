# BAR-based-Hybrid-Deep-Learning-Framework-for-Bid-Rigging-Detection
# Dataset Description

This repository provides a structured dataset for research on bid-rigging detection in public procurement.  
The dataset is derived from real-world procurement records from the Korean Public Procurement Service (PPS) and legally confirmed bid-rigging cases issued by the Korean Fair Trade Commission (FTC).  

To ensure reproducibility while respecting legal and ethical constraints, the data are anonymized and released in a structured, research-oriented format suitable for machine learning and deep learning studies.

---

## Data Structure Overview

The dataset is organized into three complementary components, reflecting different analytical levels of the bidding process: bid-level information, first-ranked bidder information, and competing bidder information.

---

### 1. Bid-level data (`data_bid_level.csv`)

This file contains general information at the procurement notice (auction) level. Each row corresponds to a single procurement case.

**Purpose**  
To capture institutional and contextual attributes of each auction, including pricing benchmarks, participation intensity, and ground-truth labels for bid rigging.

**Key characteristics**
- One row per procurement notice  
- Represents static auction-level attributes  
- Used as bid-level input features in detection models  
- Linked to bidder-level data via a common identifier  

---

### 2. First-ranked bidder data (`data_frb.csv`)

This file contains information related to the first-ranked (winning) bidder for each procurement notice.

**Purpose**  
To represent the strategic behavior of the winning bidder, which plays a central role in identifying collusive bidding patterns.

**Key characteristics**
- One row per procurement notice  
- Includes bid price and Bid Adjustment Rate (BAR) of the first-ranked bidder  
- Firm identifiers are anonymized  

---

### 3. Competing bidder data (`data_cb.csv`)

This file contains information for competing bidders ranked second through fifth in each procurement notice.

**Purpose**  
To capture relative bidding strategies and structural differences between the winning bidder and competing bidders.

**Key characteristics**
- Multiple rows per procurement notice (one per competing bidder)  
- Includes bid prices, BAR values, and bidder ranks  
- Enables analysis of relative price positioning and coordinated bidding behavior  

---

## Bid Adjustment Rate (BAR)

A core variable in this dataset is the **Bid Adjustment Rate (BAR)**, which quantitatively measures how a bid deviates from institutional pricing thresholds.

The BAR is defined as:

