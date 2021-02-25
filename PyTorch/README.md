# 安装依赖        
apt-get install libopenblas-dev cython3 libatlas-base-dev m4 libblas-dev cmake
apt-get install python3-dev python3-yaml python3-setuptools python3-wheel python3-pillow python3-numpy
# 设置环境变量
export NO_CUDA=1          
export NO_DISTRIBUTED=1            
export NO_MKLDNN=1        
export NO_NNPACK=1            
export NO_QNNPACK=1          
# 进入文件所在目录
pip3 install 文件名字
