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

> :warning: Important Reminder: Always use the Development Dashboard and Endpoints (see below) if you're testing your app.


You can create multiple apps and manage users per app using your Partner Account.

<br/>
<p align="center">
  <img width="800" src="https://raw.githubusercontent.com/XLDTechLabs/XLD-Endpoints/master/assets/apps-and-users.jpg"/>
</p>


### Keywords

1. **Partner Key** and **Client Secret** - credentials you use to identify you on our platform. Get this on your dashboard.
2. **User Key** - a unique set of characters to identify users when sending the rewards.
3. **App ID** - a unique number or username to identify an app.

<br/><br/>

# Coding Time!

<br/>

### 1. Create an App

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

### 2. Authenticating a User

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

* user_id - This is the "id" return in 2. Authenticating a User
```

```
{
   "status": "SUCCESS"
}
```
