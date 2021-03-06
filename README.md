## Firetable

Firetable is an Excel/Google Sheets like UI for Firebase/Firestore. No more building admin portal for allowing business users to access data from GCP.

#### Firetable UI

Supports fields such as images, files, single/multi select in addition to standard fields. Functions such a row resizing, data import/export are supported. More coming soon, for comprehensive list of checkout ROADMAP.
![Firetable](https://i.imgur.com/Isuhy3u.png)

## Setup instructions

#### 1) Create a firebase project ([instructions](https://console.firebase.google.com/u/0/))

- enable firestore
- setup security rules: test mode or setup required permission
- upgrade project to Blaze plan
- go to authentication/ sign method enable google auth


#### 2) Create an algolia project

- get the generated appId,API key and search key

#### 3) Clone repo

```
git clone https://github.com/AntlerVC/firetable.git
```

#### 4) Setup cloud functions

install dependencies

```
cd cloud_functions/functions;yarn
```

insure that you have firebase cli installed, [instructions](https://firebase.google.com/docs/cli)

then set cloud environment keys using the following commands

```
firebase functions:config:set algolia.appid=YOUR_APP_ID algolia.apikey=ADMIN_API_KEY
```

Deploy the cloud functions to your firebase project

```
yarn deploy
```

#### 5) Set environment variables


create a .env file in the www directory


```
REACT_APP_FIREBASE_PROJECT_NAME =
REACT_APP_FIREBASE_PROJECT_KEY =
REACT_APP_ALGOLIA_APP_ID =
REACT_APP_ALGOLIA_SEARCH_KEY =
```

#### 6) Run frontend

install dependencies

```
cd www;yarn
```

#### 7) Run project locally

```
yarn start
```
