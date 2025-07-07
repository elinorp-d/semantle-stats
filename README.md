# Semantle Head-to-Head: Elinor vs Benno

A simple, zero-setup web app for tracking daily Semantle results and friendly rivalry stats between Elinor and Benno.

---

## Features

- **Paste daily Semantle results** for both players.
- **Point-based scoring system** that rewards solving puzzles, using fewer guesses, and finding closer words.
- **Stats dashboard:** total points, win percentages, solve rates, and average "best guess" for each player.
- **Full results history** table, including winner, points awarded, and reason for each day.
- **Edit and delete** any previous entry directly in the browser.
- **Export/Import CSV** to back up or restore all data, or to use with Google Sheets/Excel.
- **All data is private and stays in your browser** (using localStorage).
- **No server or sign-in required.**

---

## How To Use

1. **Open `semantle-head2head.html` in your web browser** (double-click, or right-click and open with Chrome/Firefox/Edge/Safari).
2. **Paste your Semantle result** in the Elinor or Benno box, and click **"Add Today's Result."**
3. **See stats and history** update automatically.
4. To **edit or delete** a past entry, use the links in the Results History table.
5. To **back up or share data**, use **Export CSV** to save your history, and **Import CSV** to restore it (or load it on another device/browser).
6. **Data persists automatically** as long as you use the same browser and don't clear site data.

> **Tip:** For extra peace of mind, occasionally export your CSV and keep it in the same folder.

---

## Scoring System

Points are awarded based on performance with two decimal place precision:

1. **When both players solve the puzzle:**
   - Winner is the player who used fewer guesses
   - Points awarded = 0.01 × (loser's guesses - winner's guesses)
   - If guesses are tied, the earlier top guess breaks the tie
   - Tiebreaker points = 0.01 × (loser's top guess # - winner's top guess #)

2. **When neither player solves the puzzle:**
   - Winner is the player with the higher similarity score
   - Points awarded = 0.01 × (winner's similarity - loser's similarity)
   - If similarity is tied, the earlier top guess breaks the tie
   - Tiebreaker points = 0.01 × (loser's top guess # - winner's top guess #)

3. **When one player solves and the other doesn't:**
   - The solver automatically wins
   - Points awarded = 5.0 + 0.02 × (1000 - loser's best similarity)
   - This gives a base of 5 points plus a bonus for outperforming the opponent

---

## Limitations & Notes

- Works best for two players (Elinor and Benno).
- The app cannot automatically import your CSV without you selecting it (browser security).
- If you clear browser data, you'll lose your history unless you have exported it as CSV.
- The HTML and CSV files can be kept together in a git repo for easy versioning and backup.

---

### Example Files in Repo

- `semantle-head2head.html` — The app (open in browser)
- `semantle_elinor_benno.csv` — Your backup/exported results (can import into the app)

---

## Future Improvements (Ideas)

- Add additional charts (win streaks, progress over time)
- Auto-backup reminders or download
- Support for more than two players
- Online hosting

---

**Enjoy your Semantle rivalry!**