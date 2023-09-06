---
title: External Players in Kodi
date: 2022-08-26T18:30:00.000Z
tags:
  - AndroidTV
  - Kodi
  - JustPlayer
  - MXPlayer
description: >-
  Thiết lập các trình phát video như Just Player và MX Player để sử dụng trên
  Kodi
---

# ▶ Sử dụng trình phát bên ngoài cho Kodi

Thiết lập các trình phát video như Just Player và MX Player để sử dụng trên Kodi

## Video Players

* Cài đặt trình phát bạn chọn
* Sử dụng tên gói của trình phát làm tên tệp trong tệp cấu hình

Tôi sử dụng các trình phát bên dưới trên Android TV của mình

* [Just Player](https://play.google.com/store/apps/details?id=com.brouken.player)
  * Tôi sử dụng nó làm trình phát mặc định trên Kodi.
  * Nó phát được hầu hết các định dạng video và âm thanh.
  * Nó là mã nguồn mở và có sẵn tại [github.com](https://github.com/moneytoo/Player)
* [MX Player](https://play.google.com/store/apps/details?id=com.mxtech.videoplayer.ad)
  * Tôi sử dụng nó như một giải pháp thay thế để phát bất kỳ tệp nào không được trình phát khác hỗ trợ.
  * Để sử dụng trong Kodi, hãy nhấn giữ chuột mục cần phát và chọn tùy chọn `Play using`.

## Cấu Hình

Tạo tệp cấu hình `playercorefactory.xml` tại  `Android/data/org.xbmc.kodi/files/.kodi/userdata/`

```xml
<playercorefactory>
    <!-- players -->
    <players>
        <player name="JustPlayer" type="ExternalPlayer" audio="false" video="true">
          <filename>com.brouken.player</filename>
          <hidexbmc>true</hidexbmc>
          <playcountminimumtime>120</playcountminimumtime>
        </player>
        <player name="MXPlayer" type="ExternalPlayer" audio="false" video="true">
          <filename>com.mxtech.videoplayer.ad</filename>
          <hidexbmc>true</hidexbmc>
          <playcountminimumtime>120</playcountminimumtime>
        </player>
    </players>
    <!-- rules -->
    <rules action="prepend">
      <rule protocols="smb" player="JustPlayer" />
      <rule dvdimage="true" player="JustPlayer"/>
      <rule protocols="rtmp" player="JustPlayer"/>
      <rule protocols="rtsp" player="JustPlayer" />
      <rule protocols="sop" player="JustPlayer" />
      <rule internetstream="true" player="JustPlayer" />
      <rule video="true" player="JustPlayer"/> <!-- Default for anything else not listed -->
    </rules>
</playercorefactory>
```

## References

* External Players at [kodi.wiki](https://kodi.wiki/view/External\_players)
