# FGPA_DPU_object_detector
A image identifier implemented with FGPA to achieve fast real-time multiple object detection.

TEAM MEMBERS: Zuxiong Tan, Samyak Jain, Chenxi Li

# Project Goals:
1. Find a state-of-art multiple object detection model
2. Measure  its performance on GPU for inferencing
3. Deploy the model on FPGA DPU achieving real-time measurement
4. Measure the inferencing performance
5. Compare performances
* Make roofline plot
* Calculate memory bandwidths for the DL program on GPU and FPGA

# Similar Products:
1. NVIDIA Deep Learning Accelerator(NVDLA): 
* This is a free and open architecture that promotes a standard way to design deep learning inference accelerators. NVDLA is scalable, highly configurable, and designed to simplify integration and portability. The hardware supports a wide range of IoT devices. 
* NVDLA overview: http://nvdla.org
2. Google's Tensor Processing Unit(TPU):
* TPU is tailored to machine learning applications, allowing the chip to be more tolerant of reduced computational precision, which means it requires fewer transistors per operation. TPUs power many applications at Google, including RankBrain, used to improve the relevancy of search results and Street View, to improve the accuracy and quality of our maps and. navigation.
* TPU overview: https://cloud.google.com/blog/products/gcp/quantifying-the-performance-of-the-tpu-our-first-machine-learning-chip


## Sprint 1
* Mange to run YOLO on GPU
* Compare YOLO's performance on GPU to on CPU
* Get FPGA

## Sprint 2 (Lots of work on reverse-enginneering darknet YOLO)
* Refactor YOLO we got from https://pjreddie.com/darknet/yolo/ 
* Rewrite YOLO with DNNDK API
* 

### Results from sprint 1
* Prediction on BU SCC GPU 0.925530 seconds. 
* Prediction on CPU(single core). Intel Core i5: 19.457083 seconds.
* GPU Spec: 
	* Tesla P100 PCIe 16GB
	* Width: 64 bits 
	* Clock: 33MHz



# User Stories:
* Navigation for Robots
* Surveillance
* Self-Driving cars

Use YOLOv3 algorithm





