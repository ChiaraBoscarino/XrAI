# XrAI - Pathology Detection in Chest X-rays
The XrAI project tackles the challenge of identifying pneumonic pathologies in chest X-ray images using Convolutional Neural Networks (CNNs). It primarily focus on detecting pneumonia and tuberculosis, but the approach can seamlessly extend to other pathologies that manifest through radiologic analysis. This repository offers a set of solutions for addressing the complexities inherent in data preprocessing, model development, and result analysis and interpretation for  such models. The result of our efforts is a powerful and accurate tool that is able to discern when is possible to make informed predictions and when, on the other hand, the input data isn't informative enough for clinical assessments. 

## Key Features and Objectives

### What XrAI Offers
A set of jupyter notebooks that guide the user through the entire process of building a CNN model for pathology detection in chest X-rays. The notebooks are organized in a logical sequence that follows the steps of the process, from data preprocessing to model development and evaluation. The notebooks are designed to be modular and reusable, so that the user can easily adopt the same rationale and/or code for their own needs. 

In addition, a [report](XrAI_scientific_report.pdf) that describes the rationale behind the main choises and results is available in this repository. There you can find a detailed description of the project, including the challenges we faced and the solutions we adopted to overcome them. We would be happy to provide any additional information or clarification, as well as the dataset, upon request.

### Project Highlights

- **Dataset building**: Starting from a monolitic dataset of chest x-ray images training, validation and test subdatasets are generated using the right precautions, i.e.:
    - using a stratified sampling to ensure that the distribution of the classes is preserved,
    - ensuring that images belonging to the same patients are not present in different subdatasets, to avoid data leakage. 


- **Data Preprocessing**: The notebooks provide a range of solutions to tackle the challenges associated with preprocessing noisy data. These solutions encompass techniques for managing images that exhibit significant variability in various aspects, such as:
    - Image content, including variations in the subject's body structure, condition, and the presence of medical devices in the body area.
    - Grayscale references, encompassing both traditional and inverted contrast as well as variations in exposure.
    - Image quality, which can vary from clear to noisy, with different types of noise, shifts, cropping, and the presence of blanking patches.

Specifically, we developed a two-step processing framework. The first step involves traditional color normalization and resizing, while the second step is dedicated to enhancing image quality and reducing noise. Of these two modules, the latter one is particularly noteworthy in terms of innovation. It features an automatic noise detector and offers multiple options for implementing a denoising module, including a traditional denoising filter, a Fully Convolutional Denoising Network (FCDN), and a Denoising Autoencoder (DAE).

- **Model Development**: Multiple DL approaches have been attemped to solve the classification problem. The notebooks are structured to provide to the user a step-by-step guide to the development of each of the ANN considered in this context. This includes starting with a custom-built Convolutional Neural Network (CNN), progressing to more intricate networks trained through transfer learning methods, and ultimately combining the most effective models through ensembling techniques.

- **Model Evaluation**: Proper performance evaluation is often done hastily or not given the proper importance. Here we provide an accurate and thorough evaluation of the models' performance, including a detailed analysis of the metrics and the ROC curves. This allows us to identify the most effective models and to understand their strengths and weaknesses.

- **Confidence analysis**: Considering the significance of comprehending the level of confidence in the model's predictions, we offer an extensive examination of the confidence scores linked to each prediction. This analysis enables us to distinguish instances where the model delivers informed predictions from those where the input data lacks the necessary information for the model to make a confident judgment.

- **Model Explainability**: The notebooks also include a section dedicated to model explainability. This is done through the use of kernel visualization, Local Interpretable Model-Agnostic Explanations (LIME) technique, the Simple Activation Visualization (SAV) and the Gradient-weighted Class Activation Mapping (Grad-CAM). These techniques allow gain valueable  insights to understand the rationale behind the model's prediction and result to be powerful tools that can help identifying potential biases.

Read the [report](XrAI_scientific_report.pdf) to learn more about the techniques, the results and the insights we gained from this project.



## Authors and Acknowledgments
XrAI is the result of the collective efforts of Chiara Boscarino, Filippo Castellani, and Federico Cavallini, three master's students at Politecnico di Milano.
We developed this project within the framework of V. Corino's "[Methods & Applications of AI in Biomedicine](https://www11.ceda.polimi.it/schedaincarico/schedaincarico/controller/scheda_pubblica/SchedaPublic.do?&evn_default=evento&c_classe=788164&__pj0=0&__pj1=552e8bace80cad6c09cc7d90548cde8f ) (2022/23)" course in the Biomedical Engineering program at Politecnico di Milano. 

Feel free to reach out for any doubt or further information. We also would greatly appreciate any feedback or advice from the community. Your insights can help us improve further!
