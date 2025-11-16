# **Sentiment Analysis of Public Reactions to Indonesia’s Free Shipping Restriction Policy**

This repository contains an end-to-end social media analysis project examining public reactions to **Indonesia’s Regulation No. 8/2025** on limiting free-shipping promotions. Using more than **5,900 TikTok comments**, the study applies **Natural Language Processing (NLP)** techniques—including sentiment classification, word association analysis, and topic modeling—to understand public perception and behavioral implications.

This project was completed as part of the **Mid-Exam Assignment for the Social Media Analysis course**.

---

## 📁 Repository Structure

```
MidExam-Project/
│
├── PPT_Pembatasan-Gratis-Ongkir.pdf        # Presentation slides
├── README.md                               # Project documentation
├── SMA_Pembatasan-Gratis-Ongkir.ipynb      # Main analysis notebook
├── slang_GratisOngkir.txt                  # Slang dictionary for preprocessing
└── tiktok-ams-capstone1.csv                # TikTok comments dataset
```

---

## 🎯 Project Overview

In 2025, the Indonesian government introduced a regulation limiting free-shipping promotions to **3 days per month**. The policy aims to protect MSMEs and small logistics players, but it triggered widespread public debate—especially on TikTok, where discussions around online shopping are highly active.

This project investigates:

* How the public emotionally responds to the policy
* What key issues dominate the conversation
* How discourse evolves over time
* What insights can guide better communication and policymaking

---

## 🧪 Methodology

### **1. Data Source**

* Platform: TikTok
* Total comments: **5,967**
* File: `tiktok-ams-capstone1.csv`
* Additional lexicon: `slang_GratisOngkir.txt` for slang normalization

### **2. Preprocessing**

* Text cleaning (lowercasing, symbol/emoji removal)
* Noise filtering
* Slang normalization
* Removal of off-topic comments

### **3. Sentiment Analysis**

Three sentiment categories were modeled:

* Positive
* Neutral
* Negative

### **4. Topic Modeling**

Performed separately for each sentiment category to identify dominant discussion themes.

### **5. Visualization**

* Sentiment distribution
* Daily comment trends
* Wordlink/word association maps
* Topic summaries

All analysis steps are available in the notebook:
**`SMA_Pembatasan-Gratis-Ongkir.ipynb`**

---

## 📊 Key Findings

### **1. Sentiment Distribution**

* **Negative — 55%**
* **Neutral — 38%**
* **Positive — 6%**

Most users expressed concern about rising shipping costs and the potential impact on couriers’ income.

### **2. Word Association Highlights**

#### **Positive Themes**

* Saving money
* Offline shopping revival
* Empathy and support for couriers

#### **Negative Themes**

* Increased financial burden for consumers
* Criticism of the policy and government
* Fear of declining online shopping activity
* Concerns about courier earnings

#### **Neutral Themes**

* General discussions about parcels, delivery, payment
* Mixed or unclear comments
* Significant amount of entertainment-related noise

---

## 📈 Trend Insights

* Discussions peaked on **20–21 May 2025**, shortly after policy announcements.
* Negative sentiment surged during the peak period.
* Public attention declined sharply afterward.

---

## 🗂 Topic Modeling Summary

### **Positive**

* Cost-saving strategies
* Support for local markets and offline stores
* Appreciation for logistical workers

### **Negative**

* Anxiety over reduced buying activity
* Economic pressure on various demographic groups
* Distrust toward regulatory motives
* Issues of regional inequality (e.g., areas outside Java rarely receiving free shipping)

### **Neutral**

* Practical conversations about delivery costs
* Courier-customer interactions
* Entertainment-related distractions
* Suggestions to use VIP e-commerce features

---

## ⭐ Influential Accounts (High Engagement)

Several TikTok creators shaped the conversation, mainly those opposing the policy:

* **nabillaaptriii**
* **ooribeefsnn**
* **dioooimida**
* **itadwi123**
* **dindakest**
* **rifky_m1bb**
* **user71542340382576**

---

## 📝 Conclusion

The analysis reveals strong public resistance toward the free-shipping restriction policy. Many users worry about increased shopping costs, reduced convenience, and the financial impact on couriers. While a minority supports the idea of revitalizing offline markets, the overall sentiment indicates a **gap between policy objectives and public understanding**.

---

## 💡 Recommendations

* **Clarify policy goals** using simple, accessible communication
* **Provide support schemes** for couriers and small logistics players
* **Collaborate with e-commerce platforms** to offer affordable delivery options
* **Educate the public** to address misconceptions
* **Monitor the policy impact regularly** to ensure responsiveness

---

## 🚀 How to Run the Notebook

1. Clone the repository:

   ```bash
   git clone https://github.com/Alfa4026/academic-projects.git
   ```
2. Navigate to the project folder:

   ```bash
   cd SocialMediaAnalysis-Projects/MidExam-Project
   ```
3. Install required libraries:

   ```bash
   pip install pandas numpy nltk matplotlib seaborn scikit-learn
   ```
4. Launch Jupyter Notebook:

   ```bash
   jupyter notebook SMA_Pembatasan-Gratis-Ongkir.ipynb
   ```

---

## 🤝 Contributions

Feel free to open issues or submit pull requests for improvements, additional analysis techniques, or extended datasets.

---

