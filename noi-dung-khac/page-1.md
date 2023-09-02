# Page 1

Google TV đã ra mắt trên Chromecast mới trong tuần này, trong đó đáng chú ý nhất là màn hình chính được làm mới. Nếu bạn thích phong cách mới thì đây là cách sử dụng màn hình chính của Google TV trên thiết bị Android TV.\
[![Ảnh minh hoạ](https://1.bp.blogspot.com/-BSR3S-w1-PQ/X3fYHoxXq9I/AAAAAAAAAls/cnn500qTsMMxIWYtDYPpNsVOsJINjH4KwCLcBGAsYHQ/w320-h180/unnamed%2B%2810%29.webp)](https://1.bp.blogspot.com/-BSR3S-w1-PQ/X3fYHoxXq9I/AAAAAAAAAls/cnn500qTsMMxIWYtDYPpNsVOsJINjH4KwCLcBGAsYHQ/s1024/unnamed%2B%2810%29.webp)![](<../.gitbook/assets/image (5).png>)\


{% hint style="info" %}
_Lưu ý: Tôi không chịu trách nhiệm về bất kỳ mất mát dữ liệu hoặc lỗi nào bạn có thể gặp phải. Cẩn thận trước khi thực hiện. Tôi chỉ khuyến khích phương pháp này cho những người biết sử dụng các lệnh Android ADB.Yêu cầu thiết bị chạy Android TV 9.0 hoặc cao hơn._\
Đầu tiên bạn cần tải tệp cài đặt APK, bạn có thể sao chép vào USB/SD và dùng trình quản lý file bất kỳ (có trên store) để mở và cài đặt nó. Khuyến nghị: X-Plorer, FX File Explorer, File Explorer,...
{% endhint %}

[Tải về APK (Google TV Home)](https://www.apkmirror.com/apk/google-inc/google-tv-home-android-tv/)

\* Tab Tìm kiếm có thể sẽ không hoạt động. Để nó hoạt động, hãy cập nhật ứng dụng Google tìm kiếm mới nhất hoặc cập nhật thủ công

&#x20;[Tải về bản cập nhật Google](https://www.apkmirror.com/apk/google-inc/google-app-for-android-tv-android-tv/)\
\
HƯỚNG DẪN BẬT ADBMở Cài đặt > Giới thiệu > Build Version và nhấn liên tục phím OK cho đến khi báo Tùy chọn nhà phát triển được bật. Nhấn phím quay lại và vào menu Tùy chọn thiết bị, tìm và mở Tùy chọn nhà phát triển. Sau đó, bạn bật cả Gỡ lỗi USB và Gỡ lỗi mạng. Sau đó, quay lại menu Cài đặt > Tùy chọn thiết bị > Giới thiệu > Trạng thái để lấy địa chỉ IP của thiết bị.\
\
HƯỚNG DẪN CHO NGƯỜI DÙNG MÁY TÍNHĐầu tiên, kết nối với thiết bị bằng “adb connect” và địa chỉ IP. Sau khi chạy lệnh này, có thể bạn sẽ được yêu cầu trên Android TV cho phép máy tính của mình kết nối.

* `adb connect [địa chỉ IP]`

Ví dụ adb connect 192.168.1.2:5555\
Khi đã kết nối và sẵn sàng, tiến hành tắt Launcher mặt định. Chắc chắn rằng launcher mới của Google TV đã được cài đặt trước (nếu không sẽ lỗi vì không còn launcher nào để chạy :D).

* `adb shell pm uninstall --user 0 com.google.android.tvlauncher`

Sau khi chạy xong lệnh này, launcher của Google TV sẽ thay thế launcher gốc.Nếu bạn cần chuyển về launcher gốc của Android TV, hãy chạy lệnh này.

* `adb shell cmd package install-existing com.google.android.tvlauncher`

\
\
HƯỚNG DẪN CHO NGƯỜI DÙNG ĐIỆN THOẠI ANDROIDDùng điện thoại hoặc máy tính bảng Android và cài đặt “[Remote ADB Shell](https://play.google.com/store/apps/details?id=com.cgutman.androidremotedebugger)” từ Cửa hàng Google Play.

[![](https://1.bp.blogspot.com/-O3AavGBwvGY/X3fUHHTZMVI/AAAAAAAAAko/SLdfhKPlZugXIIGX2ho-cx4NSOmuhQEVQCLcBGAsYHQ/s320/429x158xgoogle-tv-android-tv-10.png.pagespeed.gp%2Bjp%2Bjw%2Bpj%2Bws%2Bjs%2Brj%2Brp%2Brw%2Bri%2Bcp%2Bmd.ic.ThcBMv\_KDf.png)](https://1.bp.blogspot.com/-O3AavGBwvGY/X3fUHHTZMVI/AAAAAAAAAko/SLdfhKPlZugXIIGX2ho-cx4NSOmuhQEVQCLcBGAsYHQ/s567/429x158xgoogle-tv-android-tv-10.png.pagespeed.gp%2Bjp%2Bjw%2Bpj%2Bws%2Bjs%2Brj%2Brp%2Brw%2Bri%2Bcp%2Bmd.ic.ThcBMv\_KDf.png)

Mở ứng dụng và nhập địa chỉ IP của thiết bị Android TV. (theo hướng dẫn bên trên). Giữ nguyên số Port là 5555.

[![](https://1.bp.blogspot.com/-RD1y4YvqNH0/X3fUHC84SwI/AAAAAAAAAlA/Didjx0g\_qyM7er4QMUcQfuNr2k1hpQJoQCPcBGAYYCw/s320/431x198xgoogle-tv-android-tv-1.jpg.pagespeed.gp%2Bjp%2Bjw%2Bpj%2Bws%2Bjs%2Brj%2Brp%2Brw%2Bri%2Bcp%2Bmd.ic.wws1DCjzuG.jpg)](https://1.bp.blogspot.com/-RD1y4YvqNH0/X3fUHC84SwI/AAAAAAAAAlA/Didjx0g\_qyM7er4QMUcQfuNr2k1hpQJoQCPcBGAYYCw/s651/431x198xgoogle-tv-android-tv-1.jpg.pagespeed.gp%2Bjp%2Bjw%2Bpj%2Bws%2Bjs%2Brj%2Brp%2Brw%2Bri%2Bcp%2Bmd.ic.wws1DCjzuG.jpg)

Một thông báo sẽ bật lên trên Android TV của bạn. Chọn “OK” để bật kết nối không dây.\
[![](https://1.bp.blogspot.com/--WBSv3TdFQs/X3fUH\_43ZjI/AAAAAAAAAlA/34de\_KYkoqQiBlWMg7X76lnyaNt0AFn3ACPcBGAYYCw/s320/xgoogle-tv-android-tv-2.png.pagespeed.gp%2Bjp%2Bjw%2Bpj%2Bws%2Bjs%2Brj%2Brp%2Brw%2Bri%2Bcp%2Bmd.ic.ccnx\_\_RZe2.png)](https://1.bp.blogspot.com/--WBSv3TdFQs/X3fUH\_43ZjI/AAAAAAAAAlA/34de\_KYkoqQiBlWMg7X76lnyaNt0AFn3ACPcBGAYYCw/s651/xgoogle-tv-android-tv-2.png.pagespeed.gp%2Bjp%2Bjw%2Bpj%2Bws%2Bjs%2Brj%2Brp%2Brw%2Bri%2Bcp%2Bmd.ic.ccnx\_\_RZe2.png)

Sử dụng lệnh để gỡ cài đặt Trình khởi chạy Android TV. Nhập lệnh dưới đây và nhấn Enter (_đảm bảo rằng Google TV Home đã được cài đặt trước đó_):

* `pm uninstall --user 0 com.google.android.tvlauncher`

[![](https://1.bp.blogspot.com/-50E0hFD15z0/X3fUGzPrcJI/AAAAAAAAAk8/z2IijXBMvrMP6xWb7adu3G3-GrjKT5l6ACPcBGAYYCw/s320/430x391xgoogle-tv-android-tv-3.jpg.pagespeed.gp%2Bjp%2Bjw%2Bpj%2Bws%2Bjs%2Brj%2Brp%2Brw%2Bri%2Bcp%2Bmd.ic.K8uFVxmMIm.jpg)](https://1.bp.blogspot.com/-50E0hFD15z0/X3fUGzPrcJI/AAAAAAAAAk8/z2IijXBMvrMP6xWb7adu3G3-GrjKT5l6ACPcBGAYYCw/s650/430x391xgoogle-tv-android-tv-3.jpg.pagespeed.gp%2Bjp%2Bjw%2Bpj%2Bws%2Bjs%2Brj%2Brp%2Brw%2Bri%2Bcp%2Bmd.ic.K8uFVxmMIm.jpg)

Nếu lệnh hoạt động, bạn sẽ thấy một thông báo cho biết “Success”.[![](https://1.bp.blogspot.com/-Q\_zEnpbop8Q/X3fUH6yTStI/AAAAAAAAAk8/loCj06ci1TAqonjY7-J\_WqwD45OZIlI4QCPcBGAYYCw/s320/google-tv-android-tv-4.jpg.pagespeed.ce.ie2CRqWmkL.jpg)](https://1.bp.blogspot.com/-Q\_zEnpbop8Q/X3fUH6yTStI/AAAAAAAAAk8/loCj06ci1TAqonjY7-J\_WqwD45OZIlI4QCPcBGAYYCw/s650/google-tv-android-tv-4.jpg.pagespeed.ce.ie2CRqWmkL.jpg)

Nếu bạn cần chuyển về launcher gốc của Android TV, hãy chạy lệnh này.

* `cmd package install-existing com.google.android.tvlauncher`

\
Như vậy, chỉ với vài bước đơn giản bạn đã có thể trải nghiệm Google TV Home trên thiết bị của mình, Lưu ý: một số mục có thể sẽ hoạt động không chính xác vì đây chỉ là một phần của Google TV.\
Bài viết có sử dụng một số hình ảnh & tài liệu từ: howtogeek.com, 9to5google.com. Nếu thấy hữu ích hãy chia sẻ cho mọi người nhé!
