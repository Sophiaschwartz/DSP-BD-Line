# Put the Beta Delta site on GitHub with a shared database

You need: a Google account, a GitHub account, and about 20 minutes. Everything is free.

## 1. Create the database (Firebase)
1. Go to https://console.firebase.google.com and click **Create a project**. Name it `beta-delta-line`. Turn Google Analytics off.
2. On the project home, click the web icon **</>** to add a web app. Name it anything. Skip hosting.
3. Firebase shows a block called `firebaseConfig`. Keep that tab open. You need `apiKey`, `authDomain`, `projectId`, `appId`.

## 2. Turn on the database
1. Left menu: **Build > Firestore Database > Create database**.
2. Pick a location close to you (for example `nam5` or `us-east1`). Choose **Production mode**. Click Create.

## 3. Turn on email sign-in
1. Left menu: **Build > Authentication > Get started**.
2. **Sign-in method > Email/Password**. Switch on **Email/Password** and also switch on **Email link (passwordless sign-in)**. Save.
3. **Settings > Authorized domains > Add domain**. Add `YOURUSERNAME.github.io` (your GitHub username). `localhost` is already there.

## 4. Lock it to the line
1. **Firestore Database > Rules** tab.
2. Delete what is there and paste the contents of `firestore.rules`.
3. Replace `sophia_email_here@syr.edu` with the owner's email (or delete that line). Add or remove emails as needed.
4. Click **Publish**.

Keep `firestore.rules` out of your public GitHub repo. It lists everyone's email.

## 5. Connect the page
1. Open `index.html` in any text editor.
2. Find the line starting `var FB_CONFIG=` near the top of the script.
3. Replace each `PASTE_HERE` with the matching value from step 1. Keep the quotes.

## 6. Publish on GitHub
1. On github.com click **New repository**. Name it `beta-delta-line`. Make it **Public**.
2. **Add file > Upload files** and upload only `index.html`. Commit.
3. **Settings > Pages**. Under Source choose **Deploy from a branch**, branch `main`, folder `/ (root)`. Save.
4. After a minute your site is at `https://YOURUSERNAME.github.io/beta-delta-line/`.

## 7. First visit
1. Open the site, enter your syr.edu email, tap **Email me a link**, then open the link from the email on the same device.
2. The Home page shows **Load starter data**. Tap it once to add the events, tasks, Resource Committee contacts and Week 1 jobs.
3. Send the site link to the line. Each person signs in with their own email the same way.

## Good to know
- The Firebase `apiKey` in a public repo is normal. It is not a password. The rules in step 4 are what keep strangers out.
- Anyone on the approved list can edit or delete anything. Use **Download backup** at the bottom of the page every so often.
- Sign-in emails can land in spam the first time. Ask people to check there.
- To add someone later, add their email to the rules and Publish.
- The free plan is far more than 19 people need.
