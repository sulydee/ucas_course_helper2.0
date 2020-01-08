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
3. 第三行及以后每一行为一门、是否为学位课、所属学院（0为否1为是）

如下面的为选择编号为070100M02001H（且为学位课，数学学院），081201M05002H（且为非学位课，计算机学院）

```
070100M02001H 1 数学
081201M05002H 0 计算机
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
