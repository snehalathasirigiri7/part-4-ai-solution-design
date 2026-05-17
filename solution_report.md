### Part 4: AI Solution Design for a Business Problem
1.	**Business Domain:** Healthcare  

2.	**The Business Problem:**  
Hospital process thousands of diagnostics scans every day. The numbers of patients each day are increasing and so do the number of scans and tests. These x-rays and scans often need to “wait for their turn” to be looked at by a doctor. This can cause delays and leave an urgent case waiting.  
    - Users: Doctors, Radiologists, Emergency Medicine  
    - Stakeholders: Hospital/clinic Administration, Patients  
    - Traditional Process: Even though patients are treated by order of emergency, the tests and scans are actually seen on ‘First Come, First Serve’ basis, to stay fair and organised. The scans/images are stored and reviewed in the order they were taken/received.  
    - Limitations of the traditional/current process: This manual queue does not prioritize based on severity. A critical patient might have to wait because their scan was taken after other non-critical patients, since their scans will have to be looked at first before the critical patient’s scan is seen, according to the First Come First Serve basis. This process is very slow, leading to higher mortality rates and longer hospital stays.  

3.	**AI Task Type:**  
- Image Classification (Triage Classification)  
- Triage is the process of sorting patients based on the severity of their condition to determine who needs help first. Triage classification refers to a machine learning model that automatically categorizes incoming data into priority levels.  
- The AI needs to look at x-rays and scans which are images and then classify them by order of priority. A probability score could also be assigned to every image making it more efficient reorder the scans. This allows the system to move urgent patients to the top of the doctor’s list.  

4.	**Data Requirement Plan:**  
- Type of Data Needed – Unstructured data (scan images) and structured (patient data)  
- Input features – Pixel data from images, Patient age, Type of scan, Body part  
- Target Variables – Urgency (normal, not urgent, urgent/critical)  
- Data Collection Method – Historical scans and medical records of patients, anonymised, from multiple hospital archives or storage database.  
- Data Quality Risks – Low picture quality, biased data/class imbalance (in case of rare conditions), and Variation (different doctors may label the same image differently)  

5.	**Model Recommendation:**  
- CNN (Convolutional Neural Network) or Transfer Learning Models.  
- CNNs are designed specifically to recognise patterns in images.  
- Transfer Learning Models uses a model that is already trained on millions of general images then use that to apply it on medical images/scans. Using a pre-trained model and tuning it specifically for medical data can be faster and more accurate.  

6.	**Evaluation Plan:**  
- Since, in medicine, labelling an actually sick person as ‘healthy' and missing a critical patient (False Negatives) is more dangerous than labelling a healthy patient as sick/critical (False Positives), it is important that we focus on Recall.  
- AUC-ROC can be used to measure the model’s ability to distinguish between classes.  
- An AI model can only label and sort, but it is also important that a doctor needs to be present to make the final diagnosis.  

7.	**Responsible AI Considerations:**  
- The training data should not be only from one hospital. Using a larger, diverse and central dataset should be used to increase training and variation and reduce bias.
- AI can sometimes make incorrect predictions or be biased in predictions, a human oversight would be required.  
- AI may sometimes delete files it deems as useless; hence the AI model must strictly only be allowed to rearrange and label files, ask for permissions from humans if needed.  
- The AI model can be given limited personal information such as only the scans, the age or any history or anonymise data and data encryption to ensure data privacy.  
- Doctors may stop looking closely if the AI says “Normal”. The AI model shouldn’t make diagnoses and should leave the final decision to the doctors. The AI is just an information tool and not a diagnosing tool, hence users must check the image and never over-rely on it.

**Expected Business Impact –** reduction in time to diagnose critical patients, more efficient process and time management hence higher client/customer satisfaction and more customer returns.
