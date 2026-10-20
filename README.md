# Fairview Farm Fall Classic

Live scoring app for the Fairview Farm Fall Classic: team net scoring, 3-Putt Poker, a live leaderboard and Trash Talk chat. It's a single web page hosted on GitHub Pages, with Firebase (Firestore + Authentication) as the database.

## What's in here

| File | What it is |
|---|---|
| `index.html` | The whole app |
| `firestore.rules` | Database security rules (paste into Firebase) |
| `seed.json` | Starting data: course, hole handicaps, rules settings, players, test teams and scores |
| `images/` | Default welcome photo and logo |

## One-time setup

### 1. Firestore security rules
1. Firebase console → **Firestore Database** → **Rules** tab.
2. Replace everything with the contents of `firestore.rules`.
3. Click **Publish**.

### 2. Turn on GitHub Pages
1. In this repo on GitHub: **Settings** → **Pages**.
2. Under **Build and deployment**, set Source to **Deploy from a branch**, branch **main**, folder **/ (root)**. Save.
3. After a minute the site address appears at the top of that page, e.g. `https://<your-username>.github.io/<repo-name>/`.

### 3. Allow admin sign-in from the site
1. Firebase console → **Authentication** → **Settings** → **Authorized domains**.
2. Click **Add domain** and enter `<your-username>.github.io` (no `https://`, no path).

### 4. Load the starting data
1. Open the site on your phone or computer.
2. Tap **Admin sign-in** at the bottom of the welcome screen and choose your Google account.
3. Go to **Tournament admin** → **Reset** tab → **Load starting data**. Tick "Also load the test teams and scores" if you want the practice data.

## Who can do what

- **Golfers** open the link — no account needed. They're signed in automatically in the background, so they can enter scores and chat.
- **Admin** (reidroberge8@gmail.com, signed in with Google) can manage the event, course, players, teams, photos, chat and resets.
- To add another admin, add their email to `ADMIN_EMAILS` in `index.html` **and** to the list in `firestore.rules`, then publish the rules again.

## Next year

Tournament admin → **Reset** clears scores, teams and chat while keeping players, the course and settings.
