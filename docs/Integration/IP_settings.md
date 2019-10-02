---
id: ip-settings
sidebar_label: IP Settings
title: IP Settings
---

```
Dashboard/Development/IP Settings
```
For security purposes, we built 2 secure layers: **HTTP authentication** and **IP whitelist**.
Your device's IP must be in **IP whitelist** to use GINAR services. You can manage your **whitelist** via your User Dashboard.

## Add IP address
* Add IP adress to **whitelist** separated by semicolon in the box below.
* Click **Add To WhiteList**
* Click **Save**
![IP_settings](https://github.com/GINARTeam/docs/blob/master/docs/Integration/2.IPSettings.png?raw=true)

## Delete IP address
* Click the IP which you want to delete, you will see a pop-up notification.
![delIP](https://raw.githubusercontent.com/ginarteam/docs/master/docs/Integration/delIP.png)
* Click **Save**

## Error
* If your IP is not in whitelist, you can not access to the API
```
{
    "message": "your current IP (113.161.84.237) is not whitelisted"
}
```
