介绍:

此demo的功能是用opencv的dnn模块，来运行yolov3的进行目标检测和进行OCR的，OCR模型采用的是改进版的crnn，CNN+FC。
来对检测到的目标进行识别。

检测：
检测的目标是***银行的票据。
检测的目标共有4类，分别为主键、流水号、附件及附件标题。

识别：
对检测到的目标进行识别，其中需要识别的目标有主键、流水号和附件标题。
此识别是对水平从左到有的输入有效。




采用的是cmake进行构建。对于自己写的.cpp .h文件拷贝到src文件夹下，然后在CmakeLists.txt文件中的
add_executable (detect_objects src/demo.cpp src/dataStructures.h src/***.cpp src/***.h) 后面依次添加，
然后cmake构建就可以


文件夹说明：
3rdparty:存放的是第三方库 opencv4.1.0的库
build：是已经cmake构建好的vs2015的project
data： 
	yolo文件夹：存放的是yolov3的cfg文件和weights文件，以及names文件
	ocr文件夹：存放的是ocr模型的cfg、dict和weights文件
	ocr的模型文件是在chineseOCR的ocr_dense.pth(字典大小是5530)的基础上，用实际数据进行微调得到的
test： 存放的是几张测试图片
src:   存放的是源文件


注意：
	在下载此文件后，直接运行build目录下的OpencvDarknet.sln会报错，原因是路劲错误，找不到相应文件，需要在本地重新cmake构建一下
	参见cmake截图.png
	

版本说明：
opencv4.1.0


Author:BigPanda
E-mail:wangxiong@founder.com
State Key Laboratory of Digital Publishing Technology
Date:2020-5-8 
