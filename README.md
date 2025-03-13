# Project Name
Polar Sea Ice, ICESat-2, Sea Ice Classification, Auto-labeling, Deep learning, Freeboard, Parallel Processing, Distributed Deep Learning, Synchronous Data Parallel.

## Description
ICESat-2 (IS2) by NASA is an Earth-observing satellite that measures high-resolution surface elevation. The IS2's ATL07 and ATL10 sea ice elevation and freeboard products of 10m-200m segments which aggregated 150 signal photons from the raw ATL03 (geolocated photon) data. These aggregated products can potentially overestimate local sea surface height, thus underestimating the calculations of freeboard (sea ice height above sea surface). 
To achieve a higher resolution of sea surface height and freeboard information, in this work we utilize a 2m window to resample the ATL03 data. Then, we classify these 2m segments into thick sea ice, thin ice, and open water using deep learning methods (Long short-term memory and Multi-layer perceptron models). To obtain labeled training data for our deep learning models, we use segmented Sentinel-2 (S2) multi-spectral imagery overlapping with IS2 tracks in space and time to auto-label IS2 data, followed by some manual corrections in the regions of transition between different ice/water types or cloudy regions. We employ a parallel workflow for this auto-labeling using PySpark to scale, and we achieve 9-fold data loading and 16.25-fold map-reduce speedup. To train our models, we employ a Horovod-based distributed deep-learning workflow on a DGX A100 8 GPU cluster, achieving a 7.25-fold speedup.
Next, we calculate the local sea surface heights based on the open water segments. Finally, we scale the freeboard calculation using the derived local sea level and achieve 8.54-fold data loading and 15.7-fold map-reduce speedup. Compared with the ATL07 (local sea level) and ATL10 (freeboard) data products, our results show higher resolutions and accuracy (96.56%).

Due to file size constrain, only some sample data are uploaded here.

## Table of Contents
- [Installation](#installation)
- [Contributing](#contributing)
- [Contact](#contact)

## Installation
1. Clone the repository:
   ```sh
   git clone https://github.com/jmiqra/Sentinel-2_Sea-Ice_Classification.git
   ```
2. Navigate to the project directory:
   ```sh
   cd Sentinel-2_Sea-Ice_Classification
   ```

## Contributing
1. Fork the project
2. Create a new branch (`git checkout -b feature-branch`)
3. Commit your changes (`git commit -m 'Add new feature'`)
4. Push to the branch (`git push origin feature-branch`)
5. Open a Pull Request

## Contact
Jurdana Masuma Iqrah - [jurdana.masuma@gmail.com](mailto:jurdana.masuma@gmail.com)

Paper - In proceedings 2025 IEEE International Parallel and Distributed Processing Symposium Workshops (IPDPSW)
Paper Link - [https://arxiv.org/abs/2502.02700](https://arxiv.org/abs/2502.02700)

Project Link: [https://github.com/jmiqra/Sentinel-2_Sea-Ice_Classification](https://github.com/jmiqra/Sentinel-2_Sea-Ice_Classification.git)
