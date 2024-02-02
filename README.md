# Crash prediction
## Introduction
Welcome to our project repository, where we dive into the realm of traffic accident analysis using a comprehensive dataset encompassing all recorded traffic accidents in Germany since 2016. The core idea driving this project was to pinpoint and focus on the city with the highest incidence of accidents, which led us to the bustling metropolis of Munich.

Our journey begins by procuring satellite images of Munich, from which we meticulously carve out a grid of 40m x 40m sections. These segments serve as the canvas on which we paint a picture of accident frequency, forming the basis for our categorization system. Each image is categorized based on the number of accidents occurring within its bounds, transforming raw data into a structured format ripe for analysis.

With our categories in place, we embark on the central mission of training a predictive model. The goal? To accurately forecast the category of any given image, effectively assessing the risk of traffic accidents in that area..

## Objectives
Our primary objective is to determine if we can develop a reliable model for predicting traffic accident risks, despite the inherent randomness of such events. The essential criterion for success is the model's ability to clearly differentiate between areas with no accidents and those with high accident frequencies. Achieving this level of discernment is vital, as it forms the foundation for practical applications in enhancing traffic safety and urban planning.

## Notebook Structure
Our 4 notebooks are structured as follows:

**1_ Data Preparation.**   
We consolidate traffic accident data from Germany (2016-2022) into a unified dataset. This stage focuses on merging annual CSV files, ensuring data integrity, and performing thorough cleaning and preprocessing.




**2_Explorative Data Analysis**   
In this phase, we analyze the dataset to understand accident trends and participant involvement. This deep dive guides our decision to focus on Munich for image collection and model training, given its high accident rate.


**3_Image Acquisation**   
We source high-resolution images of Munich from Atlas Bayern, process them by renaming based on coordinates, and slice them into 40m x 40m grids. Integrating accident data into these images allows us to categorize them for model training, with a selected subset saved for use in the training phase.


**4_Models**   
Our approach involves training Convolutional Neural Networks (CNNs) using satellite imagery and crash coordinates. We experiment with two categorization systems and various ResNet architectures. Each model's performance is evaluated and compared in the 'Model Evaluation' section to identify the most effective predictive model for traffic accident risks

## Data Sources
Our project is built upon two key data sources:

**Accident Data:** We have sourced extensive traffic accident data from the [Unfallatlas Statistikportal](https://unfallatlas.statistikportal.de/). This platform provides detailed records of traffic accidents across Germany, offering a rich dataset for analysis and modeling.

**Satellite Images:** The imagery for our project comes from [Bayerische Vermessungsverwaltung](https://geodaten.bayern.de/opengeodata/), which provides open access to high-quality satellite images of Bavaria. These images are crucial for visualizing and assessing the geographical context of traffic accidents in Munich.

## Installation and Setup
Setting up our project is designed to be straightforward and user-friendly. The primary requirement involves adjusting file paths to suit your local environment. Beyond this, our notebooks are configured to handle the creation of all necessary files autonomously.

## Results and Discussion
Our study on traffic accident risk prediction using satellite imagery yielded insightful results:

- Models with three risk categories outperformed the five-category models, indicating that broader categories are more distinguishable.
- ResNet 34 was the optimal architecture in the 3-category setup, striking a good balance between complexity and performance.
- The 3-category models particularly improved in predicting the middle category, a challenge in previous models.
- A consistent misclassification trend in these models was the overestimation of risk in zero-accident areas.
- This shift to a simpler categorization proved beneficial, suggesting potential for further optimization in model accuracy and efficiency.


## Further Research topics
As we look to build upon the work already accomplished, several avenues for further research present themselves. These include:

- **Expanding the Image Dataset:** Training our models with a larger and more diverse set of images could significantly enhance their learning and predictive accuracy. More data often leads to better generalization in machine learning models.

- **Exploring Different Grid Sizes:** Investigating how varying the size of the grid sections impacts model performance could provide valuable insights. Different grid sizes might capture varying levels of detail, potentially affecting the model's ability to accurately assess risk.

- **Integrating Additional Datasets:** Incorporating supplementary datasets, such as those detailing construction sites or speed limits, could add crucial context to our models. This additional information might enable a more nuanced understanding of risk factors contributing to accidents.

- **Understanding Category 0 Predictions**: A deeper analysis of how the model predicts Category 0 (no accidents), especially in areas with streets, is essential. This could help in fine-tuning the model to distinguish between visually similar yet functionally different areas, such as streets with and without a history of accidents.

These research topics aim not just to enhance the performance of our current models but also to deepen our understanding of the factors influencing traffic accidents, leading to more informed and effective predictive models.
