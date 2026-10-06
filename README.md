# CostcoTracker

CostcoTracker is a little iPhone app I built because Costco receipts are useful, but actually finding anything in them later is a pain.

It keeps your Costco purchase history in one place, lets you look up what you paid for an item before, helps spot possible price matches, keeps track of returns, and gives you a cleaner way to pull up receipt info when you're standing in the warehouse.

It started as a personal project for me, but the IPA is public if anyone else wants to use it.

> CostcoTracker is unofficial and is not affiliated with Costco Wholesale Corporation.

---

## What it can do

### See what you bought and what you paid

CostcoTracker can sync your warehouse purchases and online orders, then lets you search by Costco item number.

For each item, you can see things like:

- when you bought it
- where you bought it
- how much you paid
- how many you bought
- warehouse receipt info or online order info
- previous returns
- recorded price adjustments

There is also a purchase history screen that rolls everything together so you can see your average price, lowest price, highest price, total quantity bought, returned quantity, and a price history chart.

---

## Check for price drops

If you're in Costco and see something you already bought sitting there for less, enter or scan the item number and current shelf price.

CostcoTracker compares that against your saved purchase history and shows the difference.

If it looks worth dealing with, save it to the **Price Matches** tab so you can keep a little list while you're walking around the store.

You can also save a clean price-match card to Photos if you want the receipt details handy.

Costco rules still decide whether an adjustment is actually approved. The app is there to help you find the purchase and do the math, not pretend to be the Costco policy department.

---

## Keep track of returns

The **Returns** tab is basically a holding area for things you may want to bring back.

You can save a purchase, add a product photo, and keep the receipt information with it.

For warehouse purchases, CostcoTracker can show the actual receipt barcode when one is available.

For online orders, it shows the order number instead. It does not invent a fake barcode for an online purchase.

When you're done with an item, just swipe it away.

---

## Back up your stuff

There is a built-in backup and restore feature under **Data** on the Scan screen.

A backup saves the useful app data, including:

- receipt and purchase history
- price adjustments
- return information
- Price Match Queue
- Saved Returns
- saved return photos
- sync state

Backups use the file extension:

```text
.costcotrackerbackup
```

You can save one to iCloud Drive, On My iPhone, or anywhere else available in the Files app.

Costco login cookies and web-session data are intentionally left out of the backup.

---

# Install with SideStore

Add this source to SideStore:

```text
https://raw.githubusercontent.com/diggitydogg/CostcoTracker-Source/main/source.json
```

Once the source is added, CostcoTracker should show up like any other SideStore app and future builds can be installed as updates.

If you're using a free Apple developer account, remember that SideStore itself counts toward Apple's active-app limit.

---

# Quick start

## 1. Install the app

Install CostcoTracker from the SideStore source above and open it.

The app may ask for:

- **Camera access** for scanning
- **Photos access** for saving receipt and price-match cards

---

## 2. Sync your Costco history

Run a sync before doing much else.

The first sync may take a bit because CostcoTracker is pulling in older purchase history. After that, later syncs are much quicker.

Once synced, the app has the data it needs for price checks, purchase history, returns, and receipt lookup.

---

## 3. Check an item in the warehouse

On the **Scan** tab:

1. enter or scan the item number
2. enter the current shelf price
3. run the price check

If you bought the item before, CostcoTracker will show what you paid and whether the current price is lower.

If you only want to see old purchases and don't care about the current shelf price, enter the item number and open **View Purchase History**.

---

## 4. Save a price match

If a price difference looks interesting, save it.

It will show up in the **Price Matches** tab with the important purchase details.

Swipe left to delete one.

Use **Clear All Price Matches** when you're done with the whole list. The app asks before wiping everything.

Clearing this list does not touch your actual receipt history.

---

## 5. Save a return

Find the purchase you want, save it to **Returns**, and add a photo if that helps you remember what the thing actually is.

Swipe left when you no longer need it.

Use **Clear All Saved Returns** if you want to wipe the whole list. That also removes the return photos stored inside CostcoTracker.

Anything you deliberately saved to your normal Photos library stays there.

---

## 6. Pull up a receipt

If CostcoTracker has the actual warehouse receipt barcode, you can open it full screen for easier scanning.

Warehouse receipts and online orders are handled differently on purpose:

- warehouse purchase = receipt barcode when available
- online purchase = order number

That keeps the app from pretending one is the other.

---

## 7. Make a backup

Go to **Data** and choose **Back Up CostcoTracker**.

Save the file somewhere you trust.

I would especially make a backup before:

- moving to a new phone
- deleting/reinstalling the app
- testing a major new build
- doing anything else that feels like it might become an annoying story later

---

## 8. Restore a backup

Go to **Data** → **Restore CostcoTracker** and pick your `.costcotrackerbackup` file.

The app checks the backup before replacing anything.

If restore fails partway through, CostcoTracker is designed to roll back to the data you had before the restore started.

You may need to sign back into Costco afterward because login/session data is not part of the backup.

---

# A few things worth knowing

### This is not an official Costco app

Costco can change its website, receipt formats, APIs, or policies whenever it wants. If they change something important, syncing may need to be fixed in a future build.

### Price-match results are not guarantees

CostcoTracker can tell you what you paid, what the current price is, and what the difference looks like.

Whether Costco actually approves an adjustment is still up to Costco.

### Returns are matched by item number

The return data available from Costco does not always tell the app exactly which original purchase receipt a return belongs to.

Because of that, return quantities are reconciled at the item-number level.

### Your data is local

The working database lives on your device.

Backup files can contain detailed purchase history, so treat them like personal data and store them somewhere sensible.

---

# Updates

New builds are published through this repository's SideStore feed.

This repo contains the public distribution pieces:

```text
README.md
icon.png
source.json
```

The actual IPA files live under **Releases**.

The source code is maintained separately and is not currently open source.

---

# About this project

I built CostcoTracker for my own use because I wanted a better way to answer questions like:

- Did I already buy this?
- What did I pay last time?
- Did this get cheaper?
- Which receipt was that on?
- How many of these did I actually keep?
- What was I planning to return?

If it happens to be useful to somebody else too, great.

The prebuilt IPA is available for personal use as-is. I make no promises that Costco won't change something tomorrow and break part of it.

---

# Disclaimer

Costco, Costco Wholesale, and related marks belong to Costco Wholesale Corporation.

CostcoTracker is an independent, unofficial project. It is not affiliated with, endorsed by, sponsored by, or maintained by Costco Wholesale Corporation.

Double-check Costco's current policies before relying on the app for price adjustments, returns, or anything else Costco ultimately gets to decide.
