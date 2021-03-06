# Denoising-Autoencoder
利用卷积自编码器实现图像去噪

实验数据集：MNIST手写数字

模型结构：
	卷积自动编码器模型结构分为编码和解码过程，编码过程有6层，分别为conv1，pooling1，conv2，polling2，conv3，pooling3，解码过程相应也为6层，分别为conv4，unsample1，conv5，upsample2，conv6，unsample3。     
	在编码过程中，卷积层conv1与conv2的卷积核尺寸为3 * 3，卷积步长为1，模板深度为64，图像边缘采取0填充，卷积层conv3的卷积核尺寸为3 * 3，卷积步长为1，模板深度为32，图像边缘采用0填充。池化层pooling1，pooling2，pooling3采用最大池化层，步长为2。      
	在解码过程中，卷积层conv4的卷积核尺寸为3 * 3，卷积步长为1，模板深度为32，图像采用0填充，卷积层conv5和conv6的卷积核尺寸为3 * 3，步长为1，模板深度为64，图像采用0填充。上采样层upsample1，upsample2，upsample3上采样层，采样方式为双线性插值。     
	模型输入数据维数为28 * 28 * 1，经过第一层卷积层与池化层数据维数变为14 * 14 * 64，经过第二层卷积层与池化层数据维数变为7 * 7 * 64，经过第三层卷积层与池化层，数据维数为4 * 4 * 32，经过第一层上采样与卷积层数据维数为7 * 7 * 32，经过第二层上采样与卷积层数据维数为14 * 14 * 64，经过第三层上采样与卷积层数据维数为28 * 28 * 64。
	
![autoencoder structure](https://github.com/JackFrost168/Denoising-Autoencoder/blob/master/cae.jpg)

去噪实验效果：  
![the result of experiment](https://github.com/JackFrost168/Denoising-Autoencoder/blob/master/Autoencoder.jpg)

误差曲线图：  
![loss](https://github.com/JackFrost168/Denoising-Autoencoder/blob/master/error.jpg)
