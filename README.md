# ffmpeg-metartc
集成到metaRTC到ffmpeg，使ffmpeg支持webrtc

# metartc5编译
cd FFmpeg-n4.3.3/metartc5/metartc5  
cd libmetartccore5  
./cmake_x64.sh  
或者  
./cmake_android.sh  

  
# ffmpeg编译
将编译的libmetartccore5.a和其他第三方库放入metartc5目录里  
./configure --enable-libx264 --enable-gpl --extra-libs='-L/home/yang/FFmpeg-n4.3.3/metartc5 -lmetartccore5 -lpthread -lspeexdsp -lsrtp2 -lssl -lcrypto -ldl'  
make -j8  
