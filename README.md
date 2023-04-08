# ffmpeg-webrtc
集成到metaRTC到ffmpeg，使ffmpeg支持webrtc

# metartc6编译
cd FFmpeg-n4.3.3/metartc6/metartc6  
cd libmetartccore6  
./cmake_x64.sh  
或者  
./cmake_android.sh  


# ffmpeg compile
将编译的libmetartccore6.a和其他第三方库放入FFmpeg-n4.3.3/metartc6/目录里  

./configure --enable-libx264 --enable-gpl --extra-libs='-L/path/FFmpeg-n4.3.3/metartc6 -lmetartccore6 -lpthread -lsrtp2 -lssl -lcrypto -ldl'  
make -j8  



# 推流命令
如srs whip url:http://192.168.0.105:1985/rtc/v1/whip/?app=live&stream=livestream  
ffmpeg ......-acodec opus -strict -2 -ar 48000 -f webrtc "http://192.168.0.105:1985/rtc/v1/whip/?app=live&stream=livestream"  
ffmpeg ......-acodec opus -strict -2 -ar 48000 -f webrtc "webrtc://192.168.0.105:1985/rtc/v1/whip/?app=live&stream=livestream"  

# 拉流命令
srs whep url:  
ffplay "webrtc://192.168.0.105:1985/rtc/v1/whip-play/?app=live&stream=livestream"  




