![waving](https://capsule-render.vercel.app/api?type=waving&height=300&text=SOS:%20Symphony%20of%20Seismics&desc=2024%20NASA%20Space%20App%20Challenge&fontAlign=50&fontAlignY=40&color=gradient&fontSize=50)


# About the Team

We are a team of 5 Computer Science students and 1 Designer. 5 of us have experience as Visiting Scholars at Purdue University, USA! Let’s create something amazing together and have a great time doing it!

---

# SOS: Symphony of Seismics


## High-Level Summary

Our mission, "SOS: Symphony of Seismics," for NASA Space Apps Challenge 2024, aims to detect and analyze seismic events on Earth and Mars. Using **GAN** for data augmentation and **U-Net** for noise removal, we ensure precise seismic signal extraction and high accuracy, even with limited resources. We account for Martian environmental factors like thin atmosphere, extreme temperature variations, and low pressure to avoid confusing seismic signals with noise. An algorithm extracts only noise-free signals, reducing power consumption of the probe. Our technology could also be adapted for use on other planets in the future.

---

## Project Demo

[Google Slides Demo](https://docs.google.com/presentation/d/1O2X6qrV05pq8kKATUXwZRvAKD0INU_J7BAv_eogaAOs/edit?usp=sharing)

## Final Project

[Download Project](https://drive.google.com/file/d/1VS7iOHMF_6Wb8eX9DZOEtvks97E6RFOJ/view?usp=sharing)

---

## Project Details

### Introduction

Our team consists of five passionate computer science students and one designer. Having first met in the United States, we are joyfully collaborating on this project in Korea, leveraging our diverse backgrounds and expertise. In the challenge presented by NASA, we developed a deep learning model focused on effectively detecting Mars seismic signals based on the InSight Lander's Mars data and related research.
Let’s dive into the story of our adventure!

---

### Our Goal

Our goal is to address the issue of high power consumption when transmitting earthquake data from Mars to Earth while also enabling accurate seismic detection. To achieve this, we aim to develop an algorithm that effectively separates noise from seismic signals caused by environmental factors such as wind, air pressure, and temperature. The proposed deep learning model integrates **GAN-based data augmentation** and **U-Net for noise removal** to extract accurate and reliable seismic signals. This approach not only reduces unnecessary data transmission and minimizes power consumption but also enhances the accuracy of seismic signal detection, thereby increasing the reliability of seismic activity analysis and forecasting. Ultimately, this technology will significantly improve data transmission efficiency for future space exploration missions, enabling more extensive data analysis and exploration, and serving as a crucial turning point in the field.

---

### Why We Use Environmental Data Additionally?

In our project, we incorporated environmental variables to clearly distinguish seismic signals from environmental noise. Failing to consider these environmental factors—such as wind, temperature, and atmospheric pressure—can lead to confusion between environmental noise and actual seismic signals, resulting in incorrect conclusions.

- **Very Thin Atmosphere**: Mars' atmospheric pressure is only about 0.6% of Earth's, significantly impacting seismic data.
- **Extreme Day-Night Temperature Variations**: These fluctuations introduce additional noise into seismic signals.
- **Wind Speed**: Mars experiences strong winds, especially during daytime hours, contributing to environmental noise in seismic data.
![image](https://github.com/user-attachments/assets/e3a27cb1-d663-4c79-931d-fa25aa185585)
Seismic data collected through SEIS & Pressure data collected through a Pressure Sensor
![image](https://github.com/user-attachments/assets/b1d4b73e-3d59-41b6-a349-7a4afe3a300f)
Wind speed and temperature data collected through the TWINS Sensor
During the "day" period, we can observe an increase in seismic wave amplitude, which may be associated with rising temperatures, dropping atmospheric pressure, and strong winds. Therefore, by integrating these environmental variables into our models, we ensure accurate detection of seismic signals and effective removal of environmental noise, thereby securing reliable seismic data.

---

### Seismic Signal Analysis Model Based on Environmental Noise Removal Using GAN and U-Net

Our project sequentially employs two models to effectively analyze and extract seismic signals:
1. **GAN** (Generative Adversarial Network) for data augmentation.
2. **U-Net** for noise removal to extract accurate seismic signals.

This GAN -> U-Net combination is optimized for distinguishing between signals and noise in complex data, making it highly suitable for detecting fine seismic patterns and ensuring precise analysis of seismic data from both Earth and Mars.

#### Data Augmentation (Using GAN)
![image](https://github.com/user-attachments/assets/eebd301c-3aec-407f-8478-afb5a20c0b30)

GAN is a model that generates images, videos, music, or sentences through adversarial training between a Generator and a Discriminator.

- **Problem** : When classifying data with low SNR as signals containing noise such as wind, and data with high SNR as seismic data, there were only 13 seismic events identified.
- **Generation of Diverse Data with Low Dependency on Original Data** : GAN can generate new data with diverse features, free from any biases present in the training data. This ensures that U-Net does not overfit to specific environments or conditions, allowing it to learn a broader range of patterns that may occur in different scenarios.
- **Generation of Large Training Sets** : By utilizing the diverse data generated by GAN for U-Net training, we can significantly expand the amount of training data available. This helps U-Net become a more adaptable model, capable of generalizing to various real-world conditions and seismic events.

#### Original Data
![image](https://github.com/user-attachments/assets/cd83a13d-5a75-4384-96af-fcaa43b62ce0)
#### Augmented Data Using GAN
![image](https://github.com/user-attachments/assets/c06c67a8-701a-43ca-831a-14293fa523a6)
Data augmented from 13 to 4000 becomes input data for U-Net.

---

#### Noise Removal and Signal Extraction (Using U-Net)
![image](https://github.com/user-attachments/assets/9fbaf490-7dd9-4c85-a554-f5a18de35f83)

U-Net is a structure that generates a mask as the output, used to separate seismic signals from noise in the input data. This allows for the extraction of precise seismic signals. Although our model is not designed for segmentation, applying ISTFT to each dataset allows us to obtain signal waveforms.

- **Detailed Feature Extraction**: Extracts critical seismic signal features from the input data. In the encoder section of U-Net, several layers are used to capture increasingly detailed features, allowing the model to learn the intricate patterns of seismic data accurately.
- **Multi-Resolution Analysis**: The U-Net architecture performs analysis at multiple resolutions through pooling and upsampling steps. This ensures that both broad data patterns and fine seismic signals are detected. This phase maintains a balance between capturing overall context and preserving small-scale details.
- **Preserving Fine Details After Noise Removal**:During the upsampling phase, previously extracted fine details are incorporated back into the model, ensuring that important information is preserved even after noise removal. This results in clean signals while retaining essential seismic features.


### Separation Noise from Quakes(Event) Using U-Net

#### Event waveform
![image](https://github.com/user-attachments/assets/a393b3b9-8d43-4b60-9705-3dbc734506d0)

#### Noise waveform
![image](https://github.com/user-attachments/assets/663f81bf-16f6-495c-a0fb-c6a1cb4d9ee8)

Check our model code in the source code section below.
---

### Web-Based Visualization Platform

#### SOS: Advanced Interplanetary Seismic Visualization

We have developed a web demo site where users can view seismic events on Earth and Mars in real time. The key feature of this website is that it applies our GAN -> U-Net model to remove noise, providing users with pure seismic data. It allows users to analyze and visualize data from extraterrestrial planets like Mars, making it easy to compare seismic occurrences between Earth and Mars.

Additionally, the website not only provides pure seismic data but also includes wind speed and temperature graphs, pressure graphs, noise waveforms, event waveforms, real-time data, seismic activity, and environmental variables. This integrated visualization platform enables comprehensive seismic analysis by considering environmental factors from both Earth and Mars.

#### Data Comparison Tools
![image](https://github.com/user-attachments/assets/df9d8e57-9b99-40d3-89b9-41959c59699b)

It offers functionalities to compare seismic data from Earth and Mars side by side, facilitating easy analysis of the differences in seismic activities between the two planets. This provides deep insights into geological disparities.

#### Comprehensive Seismic and Environmental Insights Platform
![image](https://github.com/user-attachments/assets/fdb9c623-7f39-423b-90ca-eff727836c93)
![image](https://github.com/user-attachments/assets/62858921-01a1-4e57-ae97-3e4178d45520)

It integrates a variety of visualization tools to effectively visualize and compare seismic data collected from both Earth and Mars in real-time. This platform includes Wind Speed and Temperature Graphs, Pressure Graphs, Noise Waveforms, and Event Waveforms, facilitating easy identification of correlations between seismic activities and environmental variables. Additionally, it allows for separate analysis of data from event days and non-event days, enabling researchers to conduct more in-depth analyses.

#### User-friendly Interface
The platform supports intuitive navigation, helping researchers quickly locate and analyze data.

---

### Web Technology Stack

- **JavaScript**
- **Tailwind CSS**
- **React**
- **Three.js**
- **@react-three/fiber**
- **R3D @react-three/drei**

---

## Discussions

### Key benefits

- **Integration of Multiple Environmental Variables**: By incorporating environmental variables such as wind speed, temperature, and atmospheric pressure into seismic data analysis, we can build more complex and sophisticated models compared to traditional simple seismic data analyses. This enables advanced seismic detection that reflects the influence of multiple environmental factors.
- **Noise Removal and Data Augmentation Using GAN**: Utilizing Generative Adversarial Networks (GAN) to generate diverse, unbiased data enhances the diversity of our training datasets. This prevents the model from overfitting to specific patterns and maximizes the performance of U-Net.
- **Power-Efficient Data Transmission**: Developing an algorithm that transmits only noise-free seismic signals minimizes unnecessary data transmission and reduces power consumption. This is crucial for transmitting data from planets where power resources are limited.

---

### Future Work

- **Creation of a Comprehensive Noise Removal Model**: While the current focus is on wind noise removal, both temperature and pressure may also introduce noise. We can extend the GAN to develop a model that removes composite noise caused by wind, temperature, and pressure, improving the robustness of the seismic signal detection.
- **Comparative Research of Earth and Mars Environments**: Temperature and pressure are critical in reflecting the environmental differences between Earth and Mars. By further analyzing these data, we can explore how environmental variations influence seismic patterns on the two planets, offering deeper insights into planetary seismology.
- **Real-Time Seismic Prediction System**: By collecting and analyzing environmental data in real-time, we could extend our system to not only detect but also predict seismic events. Exploring correlations between temperature, pressure fluctuations, and seismic activity could lead to the development of future predictive models.


---

### Team Photo

![image](https://github.com/user-attachments/assets/58bdbf71-c44b-4d9d-9d0a-2723ad054349)


---

## Source Code

- [GitHub Repository - Main](https://github.com/2024-NASA-Challenge-Neon-Cactus/Neon-Cactus.git)
- [GitHub Repository - Develop Branch](https://github.com/2024-NASA-Challenge-Neon-Cactus/Neon-Cactus/tree/develop)

---

## Use of Artificial Intelligence

- **ChatGPT**
- **Microsoft Copilot**

---

# References

## Data Sources

- **[Mars InSight Seismic Data](https://pds-geosciences.wustl.edu/insight/urn-nasa-pds-insight_seis/data/xb/)** - [NASA]  
  

- **[Mars APSS PS Data (Pressure)](https://pds.nasa.gov/ds-view/pds/viewBundle.jsp?identifier=urn%3Anasa%3Apds%3Ainsight_ps&amp;version=3.2)** - [NASA]

- **[Mars APSS TWINS Data (Wind & Temperature)](https://pds.nasa.gov/ds-view/pds/viewBundle.jsp?identifier=urn%3Anasa%3Apds%3Ainsight_twins&amp;version=3.2)** - [NASA]

- **[Earth Seismic Data](https://ds.iris.edu/ds/nodes/dmc/software/downloads/pyweed/)**

- **[Earth Pressure and Wind Data from Meteostat](https://dev.meteostat.net/python/)** - [Meteostat Python Library]

## Figures

- **fig1**: [NASA Space Apps 2024 Seismic Detection Challenge](https://www.spaceappschallenge.org/nasa-space-apps-2024/challenges/seismic-detection-across-the-solar-system/?tab=details)

- **fig2**: [DALL-E 2 by OpenAI](https://openai.com/index/dall-e-2/)

- **fig3**: [The Science Plus Article](https://m.thescienceplus.com/news/newsview.php?ncode=1065609701399548)

- **fig4, fig5**: [NASA Cutaway of SEIS](https://science.nasa.gov/resource/cutaway-of-seis/)

- **fig6**: [GAN](https://www.researchgate.net/profile/Hamed-Alqahtani/publication/337876790_AN_ANALYSIS_OF_EVALUATION_METRICS_OF_GANS/links/5df03cf3299bf10bc351ab62/AN-ANALYSIS-OF-EVALUATION-METRICS-OF-GANS.pdf)

- **fig7**: [U-Net](https://link.springer.com/chapter/10.1007/978-3-319-24574-4_28)

## Web

### Technology Stack
- JavaScript
- Python
- Tailwind CSS
- React
- FastAPI
- Three.js
- @react-three/fiber
- R3D @react-three/drei


