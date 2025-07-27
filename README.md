

#hass #PTR
1. 屏蔽hass发出的大量PTR请求/ block mass PTR req from hass
   分配一个/32地址然后用nmcli给正常的静态路由，1小时只会有1条对这个/32地址的PTR请求。
   assign a /32 addr for hass and specify a static route for hass.

2. 缓解ConnectivityCheck/ Mitigate ConnectivityCheck
   本来只用改/etc/NetworkManager/NetworkManager.conf，把间隔改大就行，但是haos用的erofs，找不到地方改读写，所以只能用busctl禁用了。
   改之前10分钟4次，改之后1小时1次。
   busctl set-property org.freedesktop.NetworkManager /org/freedesktop/NetworkManager org.freedesktop.NetworkManager ConnectivityCheckEnable b false
   

   
