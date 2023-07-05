# twilio-screenshots
Twilio提供了强大的实时视频通信功能。你可以使用Twilio的API在应用程序中实现视频通话、多方视频会议和屏幕共享。
由於twilio庫沒有提供官方的抓幀的api函數，那就需要自己實現抓帧截图的動作，
目前的思路是獲取到拉流渲染出來的buffer，获取到YUV数据转为ARGA数据，再转为Bitmap

twilio渲染的帧buffer为自定义的VideoFrame结构体。分别能得到：

ByteBuffer yData;

ByteBuffer uData;

ByteBuffer vData;

int strideY;

int strideu;

int stridev;

使用方法：

final byte[] rgba = new byte[width * height * 4];

YuvWarpManager.getInstance().getRGBA(yData, strideY, uData, strideU, vData, stridev, rgba, width, height);

引入库：

implementation 'com.oceanhub.sc:twilio-snapshot-screen:1.0.0@aar'


                                   

