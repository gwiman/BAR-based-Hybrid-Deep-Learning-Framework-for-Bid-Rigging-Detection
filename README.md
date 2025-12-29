# BAR-based-Hybrid-Deep-Learning-Framework-for-Bid-Rigging-Detection
# Dataset Description[data_bid_level.csv](https://github.com/user-attachments/files/24364134/data_bid_level.csv)


This repository provides a structured dataset for research on bid-rigging detection in public procurement.  
The dataset is derived from real-world procurement records from the Korean Public Procurement Service (PPS) and legally confirmed bid-rigging cases issued by the Korean Fair Trade Commission (FTC).  


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

### 2. First-ranked bidder data 

This file contains information related to the first-ranked (winning) bidder for each procurement notice.

**Purpose**  
To represent the strategic behavior of the winning bidder, which plays a central role in identifying collusive bidding patterns.

**Key characteristics**
- One row per procurement notice  
- Includes bid price and Bid Adjustment Rate (BAR) of the first-ranked bidder  
- Firm identifiers are anonymized  

---

### 3. Competing bidder data 

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

The BAR is defined as: BAR = (Bid Price / Base Price × 100) − MBAR


where MBAR denotes the Minimum Bid Amount Rate applied by the contracting authority.

BAR provides an interpretable indicator of bidding strategy, enabling quantitative comparison between winning and competing bidders and facilitating the detection of abnormal or coordinated bidding behaviors.

---

## Data Linking and Integrity

All three datasets are linked using a common identifier:

- `bid_notice_id`: unique identifier for each procurement notice  

This structure enables flexible modeling approaches, including:
- Bid-level classification  
- Relative bidder comparison  
- Hybrid and parallel deep learning architectures  
- Future extensions to graph-based detection models  

---

## Anonymization and Ethical Considerations

- Firm identifiers are anonymized and cannot be used to re-identify real entities.  
- Original procurement records and legally sensitive information are not publicly released.  
- The dataset is intended strictly for academic and non-commercial research purposes.  

Researchers requiring access to the full dataset for verification or extended analysis may contact the corresponding author.

---

## Intended Use

This dataset is designed to support:
- Bid-rigging detection research  
- Machine learning and deep learning model development  
- Reproducible experiments using structured procurement data  
- Policy-oriented studies on public procurement integrity  

---

## Notes

- All CSV files are encoded in UTF-8.  
- Numeric values may be scaled or normalized during model training.  
- The dataset reflects institutional characteristics of the Korean public procurement system and may require adaptation for cross-country studies.

