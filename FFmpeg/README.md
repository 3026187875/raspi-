# 安装依赖            
apt-get install yasm      
apt-get install libsdl2-dev -y    
# 下载文件       
wget http://ffmpeg.org/releases/ffmpeg-4.3.1.tar.gz 
# 解压编译        
tar -xvf ffmpeg-4.3.1.tar.gz
cd ffmpeg-4.3.1
./configure --arch=armel --target-os=linux --enable-gpl --enable-libx264 --enable-nonfree
make    
# 安装       
sudo make install   
