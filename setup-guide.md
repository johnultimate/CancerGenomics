# 🌟 Cancer Genomics Research Project - Setup Guide

*This document provides a step-by-step guide for setting up the Cancer Genomics research project. Follow these steps to configure your system, organize your repository, and prepare for whole-genome mutation analysis.*

---

## **🛠️ Step 1: Install Required Software**

### **1.1 Install Conda (Miniconda Recommended)**

- Download and install Miniconda ([Miniconda Download](https://docs.conda.io/en/latest/miniconda.html))

```bash
# Install Miniconda (Linux)
wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh
bash Miniconda3-latest-Linux-x86_64.sh
source ~/.bashrc
```

- **Verify Conda installation:**

```bash
conda --version
```

### **1.2 Create a GitHub Account & Repo**

- Sign up at [GitHub](https://github.com/)
- **Create a new repository** named `CancerGenomics`
  - Description: "Open-source cancer genomics research using bioinformatics & real mutation data."
  - Initialize with a `README.md`

---

## **🔧 Step 2: Clone the GitHub Repository**

```bash
git clone https://github.com/johnultimate/CancerGenomics.git
cd CancerGenomics
```

---

## **📚 Step 3: Install Jekyll for Research Blog**

### **3.1 Install Ruby & Jekyll**

```bash
sudo apt update && sudo apt install -y ruby-full build-essential
gem install bundler jekyll
```

### **3.2 Initialize Jekyll**

```bash
jekyll new . --force
bundle install
```

### **3.3 Test Jekyll Locally**

```bash
bundle exec jekyll serve
```

*Check that it loads at **`http://127.0.0.1:4000/`**.*

### **3.4 Push Jekyll Setup to GitHub**

```bash
git add .
git commit -m "Initial Jekyll setup"
git push origin main
```

---

## **🌐 Step 4: Create Conda Environment for Research**

```bash
conda create -n cancer-research python=3.9 jupyterlab pandas numpy scipy seaborn matplotlib biopython -y
conda activate cancer-research
pip install ipykernel
python -m ipykernel install --user --name=cancer-research
```

### **4.1 Verify Jupyter Works**

```bash
jupyter notebook
```

*If Jupyter isn’t found, install:*

```bash
conda install -n cancer-research jupyter notebook -y
```

---

## **📁 Step 5: Organize Repo Directory Structure**

```bash
cd ~/CancerGenomics
mkdir notebooks data scripts figures docs envs
```

### **5.1 Final Directory Structure**

```
CancerGenomics/
│── _posts/             # Jekyll blog pages
│── assets/             # Static assets (CSS, images)
│── notebooks/          # Jupyter notebooks
│── data/               # Downloaded cancer genomics data
│── scripts/            # Python scripts for processing
│── figures/            # Graphs & plots
│── docs/               # Research paper + project documentation
│── envs/               # Conda environment YAML file (optional)
│── README.md           # Project overview
```

---

## **🔄 Step 6: Create Research Paper Draft**

### **6.1 Create **``** for Homepage**

```bash
nano index.md
```

Paste:

```markdown
---
layout: default
title: Cancer Genomics
---

# Open-Source Cancer Genomics Project

Welcome to the **Open-Source Cancer Genomics Project**. This site documents bioinformatics research using open-source cancer data.

## 📝 Research Projects
- [Mutation Analysis](/mutation-analysis)
- [Cancer Genomics Research Paper](/research-paper)
```

### **6.2 Create Research Paper File (**``**)**

```bash
nano _posts/research-paper.md
```

Paste:

```markdown
---
layout: post
title: "Cancer Genomics Research Paper"
date: 2025-02-25
categories: research
---

# Open-Source Cancer Mutation Analysis Research Paper

## Introduction
(We will write this as we progress.)

## Methods
(Each section will be written after the corresponding analysis.)

## Results
(Coming soon...)

## Discussion
(Coming soon...)
```

✅ **Commit & Push to GitHub**

```bash
git add .
git commit -m "Added research paper structure"
git push origin main
```

---

## **🛠️ Step 7: Add **``** to Keep Repo Clean**

```bash
touch .gitignore
nano .gitignore
```

Paste:

```plaintext
# Ignore Jekyll auto-generated files & caches
_site/
.sass-cache/
.jekyll-cache/
.jekyll-metadata/
vendor/

# Ignore Ruby dependencies (Jekyll)
Gemfile.lock

# Ignore Conda environment cache
envs/

# Ignore large datasets (optional, modify if needed)
data/*.gz
data/*.vcf
data/*.bam
```

✅ **Remove Cached Files (If Necessary)**

```bash
git rm -r --cached _site .sass-cache .jekyll-cache .jekyll-metadata vendor
```

✅ **Commit & Push**

```bash
git add .
git commit -m "Updated .gitignore to exclude Jekyll cache & auto-generated files"
git push origin main
```

---

## **🔎 Step 8: Recap Before Downloading Data**

At this point, we have: ✅ **A structured GitHub repo with a Jekyll blog**\
✅ **A Jupyter Notebook setup for bioinformatics analysis**\
✅ **A Conda environment with all necessary packages**\
✅ **A draft research paper (**``**) ready to be updated manually**

---

# **🚀 Next: Download ICGC/PCAWG Whole-Genome + RNA Expression Data**