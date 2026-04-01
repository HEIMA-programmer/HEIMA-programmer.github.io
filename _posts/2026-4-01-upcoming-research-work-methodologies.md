---
layout: post
title: "A Discussion of Future Research and Research Methodologies of identifying the research question (first 2–3 weeks)"
tags: [reflection, skills]
category: experience
---


Over the coming period, I will be conducting research on **RNA-small molecule binding affinity prediction**. Gaining an **understanding** of the field and identifying **research gaps** are crucial during the initial phase of literature review.

### **Step 1: Gain an Understanding of the Field**

First, get a clear understanding of the current state of the art in RNA-small molecule binding and identify what remains unsolved. The specific steps are:

Carefully read through all relevant papers from the lab, focusing on extracting four key pieces of information from each paper: 
- what problem it addresses
- what dataset it uses
- what the core innovation of the model is
- what limitations the authors acknowledge in the “Limitations” section. These limitations often serve as entry points for the next paper.

Then, use Google Scholar and Connected Papers to identify other significant work in the field from the past two years, paying particular attention to what competitors outside the lab are doing. While tools like Claude or ChatGPT can be used to summarize papers, **we must read the original methods and experimental sections ourselves**, as AI summaries often omit critical details.

### **Step 2: Identify Gaps**

After reading, we should be able to answer this question: **In what scenarios do existing methods perform poorly, or what information do they overlook?** Common types of gaps include: 
- existing methods failing to fully utilize certain information (e.g., the tertiary structure of RNA, the 3D conformation of small molecules)
- poor generalization on certain types of data (e.g., cold-start scenarios, RNA sequences not seen in the training set)
- a lack of interpretability in prediction results.

**Tool Recommendations:** Use Zotero to manage our literature. Use Claude to help compare methodological differences across multiple papers, but remember that AI is there to assist our thinking, not to do the thinking for us. Here’s how to use it: paste the methods sections of two papers into Claude and ask, “What are the fundamental differences between these two methods in handling RNA features?” Then, form our own judgment based on its response.
