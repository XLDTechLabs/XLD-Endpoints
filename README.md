# Welcome to XLD Endpoints

<br/>

### What is XLD Endpoints?

The library we use to:
- Authenticate via [XLoad](https://www.xload.io)
- Link accounts using Wallet Addresses similar to cryptocurrencies
- Reward XLD to users
- Convert your own Coins to XLD

<br/>
<p align="center">
  <img width="400" src="https://raw.githubusercontent.com/XLDTechLabs/XLD-Endpoints/master/assets/reward-1.jpg"/>
  &nbsp
  <img width="400" src="https://raw.githubusercontent.com/XLDTechLabs/XLD-Endpoints/master/assets/reward-2.jpg"/>
</p>

### Dashboard

Once the Account Manager gave your credentails, you can visit these dashboard.

**Development**: https://xload-development.appspot.com/endpoints<br/>
**Live**: https://www.xload.io/endpoints

> :warning: Important Reminder: Always use the Development Dashboard if you're testing your app.


### Keywords

1. **Partner Key** and **Client Secret** - credentials you use to identify you on our platform. Get this on your dashboard.
2. **User Key** - a unique set of characters to identify users when sending the rewards.
3. **App ID** - a unique number or username to identify an app.

<br/><br/>

# Coding Time!

**Development**: https://xload-development.appspot.com<br/>
**Live**: https://www.xload.io

> :warning: Important Reminder: Always use the Development Endpoints (see below) if you're testing your app.

<br/>

### 1. Create an App

You can create multiple apps and manage users per app using your Partner Account.

<br/>
<p align="center">
  <img width="800" src="https://raw.githubusercontent.com/XLDTechLabs/XLD-Endpoints/master/assets/apps-and-users.jpg"/>
</p>

You need an App ID when **Authenticating Users** on the XLD Platform found in step 2.
 
You need to set your **App Name**. The XLoad app will use this when **Rewarding Users** in step 3.

Sample: You received 10 XLD from Hello World.

```
[POST] /endpoints/app/create
```

```
Headers:
- key [String]
- secret [String]

* key is the Partner Key
* secret is the Client Secret
```
 
```
Body:
{
  "name": [String]
}
```

```
{
  "app_id": [Integer]
}
```

### 2. Authenticating a User

Use XLoad to login and create a user ID that we used **3. Reward Users**

```
[POST] /endpoints/login/device-id
```

```
Headers:
- key [String]
- secret [String]

* key is the Partner Key
* secret is the Client Secret
```
 
```
Body:
{
  "device_id": [String],
  "app_id": [String]
}
```

```
Response:
{
  "id": [String]
}
```

### 3. Reward Users

Send XLDs to your users

```
[POST] /endpoints/reward
```

```
Headers:
- key [String]
- secret [String]

* key is the Partner Key
* secret is the Client Secret
```

```
Body:
{
  "user_id": [String],
  "reward": [Double]
}

* user_id - This is the "id" returned in 2. Authenticating a User
```

```
Response:
{
   "status": "SUCCESS"
}
```

### 4. Check Balance

Check how much XLD you have left in your Developer Account

```
[GET] /endpoints/balance
```

```
Headers:
- key [String]
- secret [String]

* key is the Partner Key
* secret is the Client Secret
```

```
Response:
{
   "xld": "YOUR_XLD_BALANCE"
}
```

### 5. XLD Performance Tracking

This is used to track the Daily Active Users, Monthly Active Users, and Population per app. Call this each time users open the app only when they are logged in.

```
Headers:
- key [String]
- secret [String]

* key is the Partner Key
* secret is the Client Secret
```

```
Body:
{
  "app_id": [Integer],
  "reward": [Double]
}

* app_id - This is the "app_id" returned in 1. Create an App
```
