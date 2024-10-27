# About the Team

We are a team of 5 Computer Science students and 1 Designer. 5 of us have experience as Visiting Scholars at Purdue University, USA! Let’s create something amazing together and have a great time doing it!

---

# SOS: Symphony of Seismics


---
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

---

### Our Goal

Our goal is to address the issue of high power consumption when transmitting earthquake data from Mars to Earth while also enabling accurate seismic detection. To achieve this, we aim to develop an algorithm that effectively separates noise from seismic signals caused by environmental factors such as wind, air pressure, and temperature. The proposed deep learning model integrates **GAN-based data augmentation** and **U-Net for noise removal** to extract accurate and reliable seismic signals. This approach not only reduces unnecessary data transmission and minimizes power consumption but also enhances the accuracy of seismic signal detection, thereby increasing the reliability of seismic activity analysis and forecasting. Ultimately, this technology will significantly improve data transmission efficiency for future space exploration missions, enabling more extensive data analysis and exploration, and serving as a crucial turning point in the field.

---

### Why We Use Environmental Data Additionally?

In our project, we incorporated environmental variables to clearly distinguish seismic signals from environmental noise. Failing to consider these environmental factors—such as wind, temperature, and atmospheric pressure—can lead to confusion between environmental noise and actual seismic signals, resulting in incorrect conclusions.

- **Very Thin Atmosphere**: Mars' atmospheric pressure is only about 0.6% of Earth's, significantly impacting seismic data.
- **Extreme Day-Night Temperature Variations**: These fluctuations introduce additional noise into seismic signals.
- **Wind Speed**: Mars experiences strong winds, especially during daytime hours, contributing to environmental noise in seismic data.

---

### Seismic Signal Analysis Model Based on Environmental Noise Removal Using GAN and U-Net

Our project sequentially employs two models to effectively analyze and extract seismic signals:
1. **GAN** (Generative Adversarial Network) for data augmentation.
2. **U-Net** for noise removal to extract accurate seismic signals.

This GAN -> U-Net combination is optimized for distinguishing between signals and noise in complex data, making it highly suitable for detecting fine seismic patterns and ensuring precise analysis of seismic data from both Earth and Mars.

#### Data Augmentation (Using GAN)

GAN is a model that generates images, videos, music, or sentences through adversarial training between a Generator and a Discriminator.

- **Diverse Data Generation**: GAN generates new data with diverse features, avoiding overfitting to specific environments.
- **Expanded Training Sets**: GAN-augmented data increases the amount of training data for U-Net, enabling it to adapt to various real-world conditions.

#### Noise Removal and Signal Extraction (Using U-Net)

U-Net outputs a mask that separates seismic signals from noise, enabling the extraction of precise seismic signals.

- **Detailed Feature Extraction**: U-Net captures intricate patterns of seismic data.
- **Multi-Resolution Analysis**: U-Net detects broad and fine seismic signals through pooling and upsampling.
- **Preserving Fine Details After Noise Removal**: The model preserves essential seismic features even after noise removal.

---

### Web-Based Visualization Platform

#### SOS: Advanced Interplanetary Seismic Visualization

We have developed a web demo site where users can view seismic events on Earth and Mars in real-time. This website applies our GAN -> U-Net model to remove noise, providing users with pure seismic data and allowing easy comparison of seismic occurrences between Earth and Mars.

#### Data Comparison Tools

Our platform allows side-by-side comparison of seismic data from Earth and Mars, providing insights into geological differences.

- **User-friendly Interface**: The platform supports intuitive navigation, helping researchers quickly locate and analyze data.

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

### Key Benefits

1. **Integration of Multiple Environmental Variables**: Incorporating factors like wind speed, temperature, and pressure for advanced seismic detection.
2. **Noise Removal and Data Augmentation Using GAN**: Generating diverse, unbiased data prevents model overfitting.
3. **Power-Efficient Data Transmission**: Transmitting only noise-free seismic signals reduces power consumption, crucial for space missions.

---

## Future Work

- **Comprehensive Noise Removal Model**: Expanding GAN to remove composite noise from wind, temperature, and pressure.
- **Comparative Research of Earth and Mars Environments**: Investigating environmental influences on seismic patterns.
- **Real-Time Seismic Prediction System**: Using environmental data to predict seismic events.

---

### Team Photo

![Team Photo](upload_image.12:46:07.986334)

---

## Source Code

- [GitHub Repository - Main](https://github.com/2024-NASA-Challenge-Neon-Cactus/Neon-Cactus.git)
- [GitHub Repository - Develop Branch](https://github.com/2024-NASA-Challenge-Neon-Cactus/Neon-Cactus/tree/develop)

---

## Use of Artificial Intelligence

- **Chat GPT**
- **Microsoft Copilot**

---

## Space Agency Data

- **[NASA] Mars InSight Seismic Data**
- **[NASA] Mars APSS PS Data**
- **[NASA] Mars APSS TWINS Data**
- **Earth Seismic Data**
- **Earth Pressure, Wind Data from Meteostat**

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


