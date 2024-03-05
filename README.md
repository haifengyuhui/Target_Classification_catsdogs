# Target_Classification_catsdogs
This project is to realize the image recognition of image cat and dog based on tensorflow and CNN.
----------------------------------------------------------------------------------------------
目录：

1 猫狗识别简单实现：
1.1 指定数据路径（训练集和验证集）；
1.2 数据预处理：归一化图像ImageDataGenerator、训练生成器flow_from_directory、测试生成器flow_from_directory；
1.3 构建卷积神经网络：模型Sequential（Conv2D、MaxPooling2D、Flatten、Dense）、summary、配置训练器compile；
1.4 训练网络模型：model.fit；
1.5 效果展示

2 过拟合问题解决方案（数据增强PIL或opencv）：
2.1 导入数据（PIL）；
2.2 将图像变成相同大小：flow_from_directory(save_to_dir = os.path.join(in_path, 'resize'), ......)

3 猫狗识别简单实现（数据增强改进）：
3.1 指定数据路径（同1.1）；
3.2 数据预处理：加入数据增强ImageDataGenerator(rotation_range = 40, width_shift_range = 0.2, ......)；
3.3 构建卷积神经网络（同1.3）；
3.4 训练网络模型（同1.4）；
3.5 效果展示（同1.5）

4 猫狗识别简单实现（dropout改进）：
4.1 指定数据路径（同3.1）；
4.2 数据预处理（同3.2）；
4.3 构建卷积神经网络：在全连接层中使用tf.keras.layers.Dropout；
4.4 训练网络模型（同3.4）；
4.5 效果展示（同3.5）

5 迁移学习：
5.1 指定数据路径（同4.1）；
5.2 数据预处理（同4.2）；
5.3. 构建卷积神经网络（导入模型）：from tensorflow.keras.applications.resnet import ResNet101 ；
5.4 构建卷积神经网络（定义callback）：Flatten、Dense、Dropout、Model、compile；
5.5 训练网络模型（加入callback模块）：fit(callbacks = [callback], ......)；
5.6 效果展示（同4.5）

6 制作TFRecords：
6.1 转化实例：tf.train.BytesList、tf.train.FloatList、tf.train.Int64List；
6.2 制作方法：tf.train.Example、tf.train.Features、SerializeToString()、with tf.io.TFRecordWriter(filename) as writer、writer.write()；
6.3 加载文件：tf.data.TFRecordDataset

7 图像数据处理的TFRecords实例：
7.1 读取数据和展示图像：mping.imread；
7.2 制作TFRecords(一张图片样本)：tf.image.decode_jpeg、tf.train.Example、tf.train.Features、with tf.io.TFRecordWriter(filename) as writer、writer.write()、tf.data.TFRecordDataset；
7.3 解析TFRecords：tf.io.parse_single_example、tf.image.decode_jpeg、raw_train_dataset.map；
7.4 制作训练集：shuffle、enumerate输出、tf.keras.Sequential（Flatten、Dense）、compile、fit
