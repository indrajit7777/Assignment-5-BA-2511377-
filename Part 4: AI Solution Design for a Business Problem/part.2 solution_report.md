# Part 4: AI Solution Design for a Business Problem

**Domain I chose:** Healthcare  
**AI Use Case:** Medical Image Triage

## Task 1: Choose a Business Domain
I picked **Healthcare** because it is very important and AI can really help doctors save time and help patients get faster treatment.

## Task 2: Define the Business Problem
**What problem are we solving?**  
Every day, hospitals get thousands of X-ray, CT, and MRI images. Doctors have to check all of them one by one. Sometimes serious problems like fractures or lung issues get delayed because the queue is too long.

**Who are the users?**  
- Doctors and radiologists  
- Patients who need fast treatment  
- Hospital managers

**Current process:**  
All images come in a queue and doctors review them in order. They look at every image manually.

**Problems with current process:**  
- Takes too much time (sometimes more than 30 hours)  
- Doctors get tired and can miss important things  
- Too many patients, not enough doctors  
- Delays in emergency cases

## Task 3: Identify the AI Task Type
**AI Task Type:** Image classification

**Why this is suitable:**  
The AI has to look at pictures (X-rays) and decide if the case is urgent or normal. Image classification is perfect for this because it learns from patterns in the images, just like doctors do but much faster.

## Task 4: Data Requirement Plan
**What data do we need?**  
- X-ray, CT, or MRI images (the pictures)  
- Some patient details like age, gender, and symptoms

**Type of data:**  
- Unstructured data = the actual images  
- Structured data = patient information

**Target / Labels:**  
The AI needs to learn whether the image is “Urgent” or “Normal”. These labels come from expert doctors.

**How to collect data:**  
From the hospital’s image storage system (PACS). We can also use public medical image datasets to start.

**Risks:**  
- Some diseases are rare, so data can be unbalanced  
- Images from different machines may look different  
- Patient privacy is very important

## Task 5: Model Recommendation
**Recommended Model:** Transfer learning with CNN (like ResNet or EfficientNet)

**Why I chose this model:**  
CNNs are really good at understanding images. Transfer learning means we start with a model that already knows a lot about pictures, then we just teach it about medical images. This saves time and works well even with not-so-much data. This matches the reference catalog suggestion.

## Task 6: Evaluation Plan
**Technical metrics:**  
- Recall (very important – we don’t want to miss urgent cases)  
- Accuracy, Precision, F1-score

**Business metrics (from the KPI sample file):**  
- Reduce manual processing hours  
- Reduce average resolution time  
- Lower error rate  
- Improve customer satisfaction score  

From the sample data, we can expect 20-40% faster processing and happier patients.

**Failure cases:**  
If AI misses a serious case, it should always send it to a doctor.

**Human review:**  
AI only does triage. Doctors always check the final decision. Human-in-the-loop is must.

## Task 7: Responsible AI Considerations
**Possible risks:**  
- The model might work better for some age groups or genders if data is not balanced (bias)  
- Wrong prediction can delay treatment  
- Patient data is private  
- Doctors might trust AI too much and stop double-checking  

**How to fix them:**  
- Use data from different types of patients  
- Always show doctors why AI made a decision (explainability)  
- Follow privacy rules (anonymize data)  
- Keep doctors in control – AI is only a helper  
- Keep checking and updating the model regularly

## Task 8: Final Solution Summary

**Problem**  
Doctors take too long to review X-ray and scan images manually, causing delays in important cases.

**Proposed AI Solution**  
Build an AI system that automatically checks incoming medical images and tells which ones are urgent so doctors can see them first.

**Required Data**  
Medical images + basic patient information

**Model**  
CNN with transfer learning (ResNet/EfficientNet)

**Expected Business Impact**  
- Faster image review (less backlog)  
- Doctors focus on serious cases  
- Better patient care and satisfaction  
- Saves hospital time and money

**Risks & Mitigation**  
Bias and privacy risks handled by diverse data, human review, and strict privacy rules.

