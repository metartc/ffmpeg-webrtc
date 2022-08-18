# ffmpeg-metartc
集成到ffmpeg的metaRTC

编译metartc5时  
修改include/yang_config.h   
#define Yang_HaveDatachannel 1  
将Yang_HaveDatachannel设为0  

编译mbedtls3用cmake编译  
编译libsrtp也用cmake编译  
  

./configure --enable-libx264 --enable-gpl --extra-libs='-L/home/yang/FFmpeg-n4.3.3/metartc5 -lmetartccore5 -lpthread -lspeexdsp -lsrtp2_mbed -lmbedtls -lmbedx509 -lmbedcrypto -ldl'  
