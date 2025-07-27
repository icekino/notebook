

#hass #PTR
1. block mass PTR req from hass

   assign a /32 addr for hass and specify a static route for hass.

3. disable ConnectivityCheck

   file： /etc/NetworkManager/NetworkManager.conf Read-only. 
    busctl set-property org.freedesktop.NetworkManager /org/freedesktop/NetworkManager org.freedesktop.NetworkManager ConnectivityCheckEnable b false
