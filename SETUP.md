# Putting your wish list online

About 15 minutes, all free. You'll make two accounts: **Firebase** (stores gifts and claims) and **GitHub** (hosts the page). You need two files from this folder: `index.html` and `firestore.rules`.

Shortcut: do Part 1, then paste the `firebaseConfig` block and your Google email into the chat, and Claude will fill in both files for you.

## Part 1: Firebase (the database)

1. Go to https://console.firebase.google.com and sign in with your Google account.
2. Click **Create a project**, name it something like `matthew-wishlist`, and turn **off** Google Analytics. Click **Create project**.
3. In the left menu, open **Build > Firestore Database** and click **Create database**. Choose a US location and **Start in production mode**.
4. Open the **Rules** tab. Delete what's there and paste in everything from `firestore.rules`. Change `YOUR_EMAIL@gmail.com` to your Google email, then click **Publish**.
5. In the left menu, open **Build > Authentication** and click **Get started**. Under **Sign-in method**, turn on **Anonymous**, then add **Google** and turn it on too.
   - Anonymous lets family claim gifts without making an account.
   - Google lets you sign in as the owner to edit the list.
6. Click the gear icon, then **Project settings**. Under **Your apps**, click the **</>** (Web) icon, name it `wishlist`, and leave Firebase Hosting unticked. Click **Register app**.
7. Copy the `firebaseConfig` values it shows you.
8. Open `index.html` in a text editor (TextEdit or Notepad works). Near the top of the script there's a `SETUP` section. Paste your values over the `PASTE_...` placeholders, and put your Google email in `OWNER_EMAIL`. Save the file.

## Part 2: GitHub Pages (the website)

1. Make a free account at https://github.com.
2. Click **+** at the top right, then **New repository**. Name it `wishlist`, set it to **Public**, and click **Create repository**.
3. Click **uploading an existing file**, drag in `index.html`, and click **Commit changes**.
4. Open the repo's **Settings**, then **Pages**. Under **Source**, pick **Deploy from a branch**, choose `main` and `/ (root)`, and click **Save**.
5. After a minute your site is live at `https://YOUR-GITHUB-NAME.github.io/wishlist/`.

## Part 3: Connect them and load your gifts

1. In Firebase, go to **Authentication > Settings > Authorized domains** and click **Add domain**. Enter `YOUR-GITHUB-NAME.github.io`.
2. Open your site and scroll to the bottom. Click **Owner sign-in** and sign in with Google.
3. Click **Load my starter list** to add your 9 gifts. You can also fill in **Edit About Me** while you're there.
4. Send the link to your family.

## Good to know

- **Surprise mode:** when you're signed in, the page hides who claimed what. Use **Peek at claims** if you need to check.
- **Pictures:** open a gift with **Edit**, then paste a product photo's address into **Picture link**. To get one, right-click the photo on the store's page and choose "Copy image address."
- **Undoing a claim:** people can undo their own claim from the same phone or computer they claimed on. You can remove any claim yourself.
- **The config values:** Firebase's web config isn't a password and is meant to sit in the page. The database rules are what stop anyone except you from editing gifts.
- **Updating the page later:** upload a new `index.html` to the same GitHub repo. Your gifts and claims stay in Firebase, so you won't lose them.
- **Before Part 1 is done:** the page runs in demo mode, with a yellow bar at the top, and only saves to the browser you're using.
