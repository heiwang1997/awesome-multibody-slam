# awesome-multibody-slam
Selected paper list for dynamic slam with multiple moving (rigid) objects. Both multibody motion segmentation and SLAM/VO are popular topics but the combination of them seems unexplored in the literature. This repository aims at updating recent research progress on Multibody/Dynamic SLAM and will annotate each work with tags and comments for future reference.

## 2019

**MID-Fusion: Octree-based Object-Level Multi-Instance Dynamic SLAM.** ICRA 2019.

- Dense system using octree-based representation. Utilize motion, semantic and geometry cues to perform segmentation.

**Pointflownet: Learning representations for rigid motion estimation from point clouds.** CVPR 2019.

- Detects motions between adjacent frames in LIDAR data with Multi-task CNN.

**CubeSLAM: Monocular 3D Object SLAM.** TR 2019.

- Based on 2D bbox detection. Use multi-frame BA to refine 3D bbox parameters. Dynamic contents are first associated in bbox level then the sparse landmarks are tracked using KLT.

## 2018

**Stereo Vision-based Semantic 3D Object and Ego-motion Tracking for Autonomous Driving.** ECCV 2018.

- Tracking-by-detection with 2D bbox input. Feature association relies on bbox association. BA considers sparse features, car dimension prior, bbox reprojection, vehicle motion model and PC alignment.

**Multimotion Visual Odometry (MVO): Simultaneous Estimation of Camera and Third-Party Motions.** IROS 2018.

- Libviso for tracklet generation. Construct NN Graph and optimize motion segmentation labels over the graph. Multiframe RANSAC is used to find new rigid objects.

**Motion Segmentation by Exploiting Complementary Geometric Models.** CVPR 2018.

- Generate landmark affinity matrix using RANSAC sampling based on Fundamental, Homography and Affine models and effectively combine them using Subset Constrained Spectral Clustering.

**MaskFusion: Real-Time Recognition, Tracking and Recognition of Multiple Moving Objects.** ISMAR 2018.

- Dense SLAM system using asynchronous MaskRCNN and geometric cues for motion segmentation and tracking.

**Robust Dense Mapping for Large-Scale Dynamic Environments.** ICRA 2018.

- DynSLAM System. Use semantic labels for segmentation and libviso for tracking multiple cars. 

**CarFusion: Combining Point Tracking and Part Detection for Dynamic 3D Reconstruction of Vehicles.** CVPR 2018.

- First detect car key points. Then perform BA using keypoint reprojection, link-length consistency and left-right symmetry cost. Optimized keypoint can be further employed to re-train keypoint detector.

## 2017

**Joint 3D Reconstruction of a Static Scene and Moving Objects**. TR 2017.

- Based on Pinpoint SLAM using sparse features and geometric segments. Can only detect one moving object in the scene based on outlier rejection during registration. Dynamic contents are associated by appearance tracking from its segments.

**Bounding Boxes, Segmentations and Object Coordinates: How Important is Recognition for 3D Scene Flow Estimation in Autonomous Driving Scenarios?**. ICCV 2017.

**Co-Fusion: Real-time Segmentation, Tracking and Fusion of Multiple Objects.** ISMAR 2017.

- Motion cues (registration residual) and image appearance (SLIC) are employed to detect and segment motions.

**Shape Priors for Real-Time Monocular Object Localization in Dynamic Environments.** IROS 2017.

- Build a car keypoint detection network with CRF-style loss. Trajectories are optmized with BA using shape-constrained reprojection error, temporal smoothness, dimension prior and ground-plane prior.

**Incremental Real-Time Multibody VSLAM with Trajectory Optimization Using Stereo Camera.** IROS 2016.

- Added a backend to the IV 2011 Sparse Scene flow paper.

## Before 2015

**Object Scene Flow for Autonomouse Vehicles.** CVPR 2015.

- Assuming scene 3D structure approximated by piece-wise planar superpixels. Combinations of homogrpahies can be used to form rigid bodies. Superpixels are segmented using CRF-style data term (appearance similarity) and pariwise term (smoothness). 

**Perspective Motion Segmentation via Collaborative Clustering**. ICCV 2013.

- Define perspective motion space in two-frames and link multiple frames via collaborative clustering.

**Sparse Scene Flow Segmentation for Moving Object Detection in Urban Environments**. IV 2011.

- Perform delaunay triangulation over tracked features (5 frames). The energy of the edges are the relative velocity of two landmarks. DFS is performed on the graph for segmentation and GNN is used to track motions over long sequences.

**Realtime Multibody Visual SLAM with a Smoothly Moving Monocular Camera**. ICCV 2011.

- FAST feature tracking with large search window. Use Robust Algrebraic Segmentation for motion segmentation initiliazation. Epipolar constraint and Flow Vector Bound is used to estimate motion probability. BOT achieved via particle filter.