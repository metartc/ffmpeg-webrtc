# ffmpeg-webrtc
集成到metaRTC到ffmpeg，使ffmpeg支持webrtc

# metartc6编译
cd FFmpeg-n4.3.3/metartc6/metartc6  
cd libmetartccore6  
./cmake_x64.sh  
或者  
./cmake_android.sh  


# ffmpeg编译
将编译的libmetartccore6.a和其他第三方库放入metartc6目录里  
./configure --enable-libx264 --enable-gpl --extra-libs='-L/home/yang/FFmpeg-n4.3.3/metartc6 -lmetartccore6 -lpthread -lspeexdsp -lsrtp2 -lssl -lcrypto -ldl'  
make -j8  



# 推流命令

ffmpeg ......-acodec opus -strict -2 -ar 48000 -f webrtc webrtc://192.168.0.1/live/livestream

# 拉流命令

ffplay webrtc://127.0.0.1/live/livestream


# p2p拉流命令

ffplay webrtc://127.0.0.1:1988/live/livestream


