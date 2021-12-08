# twilio-screenshots
使用twilio 視頻通話中抓幀

由於twilio庫沒有提供官方的抓幀的api函數，那就需要自己實現抓幀的動作，目前的思路是獲取到拉流渲染出來的buffer，
保存為一幀圖片。

經實際發現獲取到的buffer是三個yuv的字節數組，然後是通過libyuv庫轉換為ARGB,在轉換成Bitmap，保存為一幀圖片
