# 国科大选课助手说明 2.0 #
```
copy from https://github.com/hrwhisper/ucas_course_helper，有一丢丢内部逻辑错误，已修改。
```
## 使用方法 ##
修改private.txt后，在控制台执行
- python main.py

### private文件说明
private.txt中，各行表示意义如下：

1. 第一行为登录选课系统的账号
2. 第二行为密码
3. 第三行及以后每一行为一门、是否为学位课（0为否1为是）、所属学院（输入汉字或代码）

如下面的为选择编号为070100M02001H（且为学位课，数学学院），081201M05002H（且为非学位课，计算机学院）

```
070100M02001H 1 数学学院
081201M05002H 0 计算机学院
```
或
```
070100M02001H 1 910
081201M05002H 0 951
```

其中2020年01月08日22:26:46的学院对应代码如下
```
910 数学学院
911 物理学院
957 天文学院
912 化学学院
928 材料学院
913 生命学院
914 地球学院
921 资环学院
951 计算机学院
952 电子学院
958 工程学院
917 经管学院
945 公共管理学院
927 人文学院
964 马克思主义学院
915 外语系
954 中丹学院
955 国际学院
959 存济医学院
946 体育教研室
961 微电子学院
962 未来技术学院
963 网络空间安全学院
968 心理学系
969 人工智能学院
970 纳米科学与技术学院
971 艺术中心
972 光电学院
967 创新创业学院
973 核学院
974 现代农业科学学院
975 化学工程学院
976 海洋学院
977 航空宇航学院
```
更新方法为进入选课系统，右侧选修课程-选择课程，然后在该页面查看源代码，即可找到如下对应关系：
```
<label for="id_XXX">YYYY</label>
```

### 注意 ###
程序假设课程不冲突，每5S尝试选课一次


## 环境说明

- python 3.5.2
- requests 2.11
- 可选环境：
  - Tesseract-OCR
  - PIL

### 环境安装方法
- pip install requests
- pip install Pillow
- 登录网址默认为 http://onestop.ucas.ac.cn/home/index ，如果为 sep.ucas.as.cn 那么需要在安装如下环境：
  - Tesseract-OCR
    - windows下安装：http://digi.bib.uni-mannheim.de/tesseract/tesseract-ocr-setup-3.05.00dev.exe
      - 安装时候勾选Registry settings
    - Linux  \  MAC OS X安装见 https://github.com/tesseract-ocr/tesseract/wiki


## 更新说明

- 提升用户体验
- 支持验证码识别
- 最近更新优化了选课逻辑，提升效率
