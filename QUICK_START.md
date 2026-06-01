# Quick Start Guide - 5 Minutes to Live App

## What You're Getting:
✅ Production-ready inventory app  
✅ Real-time Firebase database (your data)  
✅ Secure login system  
✅ Mobile app (installable on phone)  
✅ Works offline, syncs online  

---

## STEP 1: Prepare Firebase (2 minutes)

Go to Firebase Console → Firestore Database → Rules tab

**DELETE everything and paste this:**

```
rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    match /users/{uid} {
      allow read, write: if request.auth.uid == uid;
      match /products/{document=**} {
        allow read, write: if request.auth.uid == uid;
      }
    }
  }
}
```

Click **PUBLISH**

---

## STEP 2: Install Firebase Tools (1 minute)

Open your terminal/command prompt and run:

```bash
npm install -g firebase-tools
firebase login
```

A browser window will open - sign in with your Google account.

---

## STEP 3: Setup Project (1 minute)

In your terminal:

```bash
mkdir inventory-app
cd inventory-app
firebase init hosting
```

When asked:
- Project: Select **inventory-app-3037c**
- Public directory: Type **public**
- Single page app: Type **y**

---

## STEP 4: Add App Files (1 minute)

1. Create a `public` folder
2. Copy `inventory-app.html` into it
3. Rename it to `index.html`

Your folder structure should be:
```
inventory-app/
├── public/
│   └── index.html
├── firebase.json
└── .firebaserc
```

---

## STEP 5: Deploy (final touch)

In terminal, run:

```bash
firebase deploy
```

**DONE!** 🎉

Your app is live at: `https://inventory-app-3037c.firebaseapp.com`

---

## FIRST TIME USE:

1. Open the URL above
2. Click "Sign Up"
3. Enter email & password (min 6 chars)
4. Click "+ Add Product" to start

---

## INSTALL ON PHONE:

### iPhone (Safari):
Share button → Add to Home Screen

### Android (Chrome):
Menu → Install app

---

**That's it! Your inventory app is now live and synced to Firebase.** 📱
