# ffmpeg-metartc
集成到metaRTC到ffmpeg，使ffmpeg支持webrtc

# metartc5编译
git clone https://github.com/metartc/metaRTC.git  
修改include/yang_config.h   
#define Yang_HaveDatachannel 1  
将Yang_HaveDatachannel设为0  
cd libmetartccore5  
./cmake_x64.sh  
或者  
./cmake_android.sh  

# mbedtls3编译
解压metartc5/mbedtls-3.2.1.7z   
./cmake_x64.sh  
或者  
./cmake_android.sh  

# srtp编译
解压metartc5/libsrtp-2.4.2.7z     
./cmake_x64.sh  
或者  
./cmake_android.sh  
编译后可重命名libsrtp2_mbed.a  
  
# ffmpeg编译
将编译的libmetartccore5.a和其他第三方库放入metartc5目录里  
./configure --enable-libx264 --enable-gpl --extra-libs='-L/home/yang/FFmpeg-n4.3.3/metartc5 -lmetartccore5 -lpthread -lspeexdsp -lsrtp2_mbed -lmbedtls -lmbedx509 -lmbedcrypto -ldl'  
make -j8
