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

# What is DPU
* The Xilinx® Deep Learning Processor Unit (DPU) is a programmable engine optimized for convolutional neural networks. The unit includes a high performance scheduler module, a hybrid computing array module, an instruction fetch unit module, and a global memory pool module. The DPU uses a specialized instruction set, which allows for the efficient implementation of many convolutional neural networks. Some examples of convolutional neural networks which have been deployed include VGG, ResNet, GoogLeNet, YOLO, SSD, MobileNet, FPN, and many others.
* The DPU IP can be implemented in the programmable logic (PL) of the selected Zynq®-7000 SoC or Zynq UltraScale+™ MPSoC devices with direct connections to the processing system (PS). The DPU requires instructions to implement a neural network and accessible memory locations for input images as well as temporary and output data. A program running on the application processing unit (APU) is also required to service interrupts and coordinate data transfers. https://www.xilinx.com/products/design-tools/ai-inference/ai-developer-hub.html#edge

![image](https://github.com/ChainZeeLi/FPGA_DPU/blob/master/DPU.png)

# DPU Development Flow (Using DNNDK)
* The DPU requires a device driver which is included in the Xilinx Deep Neural Network Development Kit (DNNDK) toolchain.
* The DNNDK User Guide (UG1327) describes how to use the DPU with the DNNDK tools. The basic development flow is shown in the following figure. First, use Vivado to generate the bitstream. Then, download the bitstream to the target board and install the DPU driver. For instructions on how to install the DPU driver and dependent libraries, refer to the DNNDK User Guide (UG1327).https://www.xilinx.com/support/documentation/user_guides/ug1327-dnndk-user-guide.pdf

![image](https://github.com/ChainZeeLi/FPGA_DPU/blob/master/Development%20Process.png)

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
* Looked into different methods to run the given C code on an FPGA
	* Use OpenCL framework to run the code on an Intel FPGA. Can be done using the Intel FPGA SDK for OpenCL
	* Convert the code into HDL to run on a Xilinx FPGA
	   * Implement DPU on vivado and run some simulation tests

### Results from sprint 1
#### Time taken to detect obejcts on a single image
* Prediction on BU SCC GPU 0.925530 seconds. 
* Prediction on CPU(single core). Intel Core i5: 19.457083 seconds.
* GPU Spec: 
	* Tesla P100 PCIe 16GB
	* Width: 64 bits 
	* Clock: 33MHz

## Sprint 3
### System Diagram
![image](https://github.com/ChainZeeLi/FPGA_DPU/blob/master/XDNN.jpeg)

# User Stories:
* Navigation for Robots
* Surveillance
* Self-Driving cars
Use YOLOv2 algorithm

# Poster
![image](https://github.com/ChainZeeLi/FPGA_DPU/blob/master/A2_09.jpg)







