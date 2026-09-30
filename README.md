# Enhancing 6D Object Pose Estimation using RGB-D Fusion

## Overview
This repository contains the research and implementation for the "Disentangled RGB-D Pose Network". The project resolves the scale ambiguity problem inherent in RGB-only 6D object pose estimation by decoupling the process into two specialized streams. By evaluating our architecture on the LineMod dataset, our method achieved a 16x accuracy improvement over a standard monocular baseline.

## My Contributions
* Contributed to the design of the convolutional pipeline that resolves spatial scale ambiguity via geometric processing. 
* Helped optimize the decoupled learning strategy, which ultimately reduced translation error from 10.93 cm to 1.27 cm.
* Wrote several sections of the project report/paper.

## Architecture
* **ROI Extraction:** Utilizes YOLOv8 for 2D bounding box predictions to isolate Regions of Interest (ROI) from both the RGB and depth images.
* **Geometric Translation Stream:** Employs a Residual Depth CNN to predict depth corrections ($\delta_z$) relative to a geometric median anchor ($z_{med}$), rather than regressing absolute distance.
* **Semantic Rotation Stream:** Uses a late-fusion MLP to combine semantic features extracted via a ResNet-50 backbone with geometric depth embeddings to regress rotation in a continuous 6D space.

## Key Results
* **Accuracy Boost:** Achieved a mean accuracy (Acc@10%) of 81.80%, which is a 16-fold improvement over the 4.91% baseline.
* **Error Reduction:** Successfully minimized the translation error to 1.27 cm and the rotation error to $4.91^{\circ}$ by preventing gradient conflicts between geometric and semantic tasks.

## Team & Acknowledgements
This research was conducted at Politecnico di Torino. 
**Authors / Team:** Nejla Dinçer, Mustafa Burak Erkoçak, Can Ersoy, and Barış Tan Ünal.
