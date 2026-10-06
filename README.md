# CostcoTracker

CostcoTracker is an independent iOS app for tracking Costco purchases, price changes, potential price matches, returns, receipts, and item purchase history.

It is designed to make Costco purchase data easier to search, review, and act on from one place.

> **CostcoTracker is an unofficial personal project and is not affiliated with, endorsed by, or sponsored by Costco Wholesale Corporation.**

---

## What CostcoTracker does

### Purchase and receipt history
- Sync Costco warehouse purchases and online orders.
- Search stored purchases by Costco item number.
- View purchase dates, quantities, prices, warehouse/source, and receipt identifiers.
- Review an item's purchase history in one place.
- See warehouse and online purchases together while still keeping their receipt/source differences clear.

### Purchase analytics
For an item with stored purchase history, CostcoTracker can show:
- gross purchase spend;
- purchased quantity;
- returned quantity;
- net quantity;
- number of purchases;
- weighted average price per unit;
- lowest recorded purchase price;
- highest recorded purchase price;
- a purchase-price history chart.

### Price-match tracking
- Enter or scan an item number and current shelf price.
- Compare the current price against stored Costco purchases.
- See potential savings for purchases that may qualify.
- Save useful matches to a Price Match Queue.
- Review previously recorded price adjustments for the same item.
- Export price-match cards to Photos.
- Swipe to delete individual saved price matches.
- Clear all saved price matches with confirmation.

### Returns
- Find prior purchases while preparing a return.
- Save items to a Returns list.
- Store an optional local product photo with a saved return.
- Display warehouse receipt barcodes when a real receipt barcode is available.
- Show online order numbers separately instead of creating fake receipt barcodes.
- Swipe to delete individual saved returns.
- Clear all saved returns with confirmation.
- Removing saved returns also removes their locally stored product photos from the app.

### Receipt barcodes
Warehouse receipt barcodes are rendered using Interleaved 2 of 5 (I25/ITF) formatting.

Expanded receipt barcodes use a scanner-friendly full-screen presentation for easier use at the warehouse.

### Backup and restore
CostcoTracker can create a portable:

```text
.costcotrackerbackup
```

file containing:
- the local receipt/item database;
- recorded price adjustments;
- return-reconciliation data;
- Price Match Queue state;
- Saved Returns metadata;
- locally stored Saved Return product photos;
- relevant sync-state metadata.

Backups intentionally do **not** include Costco authentication cookies or web-session credentials.

Restore validates a backup before replacing current data and uses rollback protection so a failed restore does not leave the app partially restored.

---

# Install with SideStore

CostcoTracker is distributed through a SideStore-compatible source.

Add this source URL to SideStore:

```text
https://raw.githubusercontent.com/diggitydogg/CostcoTracker-Source/main/source.json
```

Once the source is added, CostcoTracker can be installed and updated directly through SideStore.

## SideStore note

With a free Apple developer account, Apple limits the number of active development-signed apps on a device, and SideStore itself counts toward that limit.

If you already use SideStore for other apps, keep that limit in mind before installing CostcoTracker.

---

# User Guide

## 1. First launch

Open CostcoTracker and allow the permissions you want to use.

The app may request access for:
- **Camera** — used for scanning Costco item numbers or shelf information.
- **Photos** — used when saving price-match or receipt cards to your photo library.

Costco login/session data is handled separately from CostcoTracker's backup system.

---

## 2. Sync your Costco purchase history

Before most of the app becomes useful, sync your Costco history.

Use the app's sync controls to retrieve:
- warehouse purchase history;
- online-order history;
- receipt/item information;
- price-adjustment data;
- return/refund information used by purchase analytics.

The first sync may take longer because the app has more historical data to collect.

Later syncs are incremental and generally much faster.

### What sync creates

Synced purchase data is stored locally on your device and powers:
- price-match checks;
- purchase history;
- price-history charts;
- return lookup;
- receipt barcode display;
- price-adjustment history;
- returned-quantity reconciliation.

---

## 3. Check a current Costco price

Use the **Scan** tab when you are looking at an item in the warehouse.

Enter or scan:
- the Costco item number;
- the current shelf price.

Then run the price check.

CostcoTracker compares the current price with your stored purchase history and can show:
- what you previously paid;
- when and where you bought it;
- quantity;
- potential savings;
- whether the saved purchase is within the app's price-match window logic;
- previous recorded price adjustments for the same item.

The app does not guarantee Costco will approve an adjustment. Final eligibility depends on Costco's current policy and the warehouse handling the request.

---

## 4. View purchase history without entering a shelf price

If you only want to review your past purchases for an item:

1. Go to the **Scan** tab.
2. Enter the item number.
3. Choose **View Purchase History**.

You can also open Purchase History from supported Price Match cards.

Purchase History includes:
- each stored purchase occurrence;
- warehouse or online source;
- date;
- unit price;
- quantity;
- gross spend;
- returned quantity;
- net quantity;
- lowest/highest price;
- weighted average price;
- price-history chart;
- recorded price adjustments;
- recorded returns.

Returns are reconciled at the item-number level because Costco's available return data does not always identify the original purchase receipt.

---

## 5. Save a potential price match

When CostcoTracker finds a purchase with a useful price difference, add it to the **Price Match Queue**.

The Price Matches tab lets you keep several items together while walking through the warehouse.

Each saved item can include:
- item number;
- item description;
- purchase date;
- warehouse/source;
- price paid;
- current price;
- potential savings;
- quantity;
- receipt or order information;
- recorded price-adjustment history.

### Delete a saved price match

Swipe left on a saved item.

The standard red iOS **Delete** action appears.

A full swipe also deletes the item.

### Clear all saved price matches

Scroll to **Clear All Price Matches**.

The app asks for confirmation before removing the whole queue.

This does **not** delete your receipt database or purchase history.

---

## 6. Save a return

Use the **Returns** tab to find and save a prior purchase you may want to return.

A saved return can contain:
- item details;
- purchase date;
- price;
- warehouse/source;
- receipt information;
- an optional locally stored product photo.

### Warehouse receipts

If CostcoTracker has a real warehouse receipt barcode, the app can display it in a scanner-friendly format.

### Online orders

Online purchases show the order number as text.

CostcoTracker does not create a fake barcode for an online order.

### Delete a saved return

Swipe left on the saved return.

The red iOS **Delete** action removes the saved return and its locally stored product photo.

### Clear all saved returns

Scroll to **Clear All Saved Returns**.

The app asks for confirmation before removing:
- all Saved Return metadata;
- all locally stored Saved Return product photos.

Photos you deliberately saved into the system Photos library are not deleted.

---

## 7. Save receipt or price-match cards to Photos

Some screens can generate a clean card for use at Costco.

Depending on the source, the card may show:
- item details;
- purchase date;
- price difference;
- warehouse/source;
- receipt barcode;
- online order number.

Warehouse and online-order cards are intentionally different so the app does not present an online order as a warehouse receipt.

---

## 8. Back up CostcoTracker

From the Scan screen, open **Data**.

Choose:

```text
Back Up CostcoTracker
```

Pick a location in the iOS Files app.

The app creates a file ending in:

```text
.costcotrackerbackup
```

A backup can include your:
- receipt database;
- item history;
- price adjustments;
- return reconciliation;
- Price Match Queue;
- Saved Returns;
- Saved Return photos;
- sync-state information.

### Recommended backup locations

Good choices include:
- iCloud Drive;
- On My iPhone;
- an external drive available through Files.

Treat the backup like personal purchase history because that is what it contains.

---

## 9. Restore a backup

Open **Data** and choose:

```text
Restore CostcoTracker
```

Select a `.costcotrackerbackup` file from Files.

CostcoTracker validates the backup before changing your current data.

You will be asked to confirm because restoring replaces the current:
- receipt database;
- saved price matches;
- saved returns;
- locally stored Saved Return photos.

If restore fails during the process, CostcoTracker attempts to roll back to the exact state you had before restore began.

Costco authentication/session data is not restored, so you may need to authenticate with Costco again afterward.

---

## 10. Updating CostcoTracker

When a new build is published, SideStore should show an available update from the CostcoTracker source.

Update CostcoTracker through SideStore as you would any other SideStore-installed app.

The app's local data should remain in place when updating normally.

Creating an occasional `.costcotrackerbackup` is still recommended before major updates or device migrations.

---

# Privacy and data handling

CostcoTracker is designed around local device storage.

Local data may include:
- Costco receipts;
- purchased items;
- prices;
- quantities;
- warehouse information;
- online order metadata;
- saved price matches;
- saved returns;
- locally stored return photos.

CostcoTracker backups do **not** intentionally include:
- Costco authentication cookies;
- web-session credentials;
- temporary cache data.

Cards explicitly saved to Photos are stored in the user's system Photos library.

Users are responsible for protecting exported backup files because they may contain detailed purchase history.

---

# Known limitations

CostcoTracker is an actively developed personal project, not an official Costco application.

Important limitations include:
- Costco can change its website, API behavior, receipt formats, or policies at any time.
- Sync behavior may require updates when Costco changes its systems.
- Price-match eligibility shown by the app is informational and not a guarantee.
- Return data may not identify the exact original purchase receipt, so return quantities are reconciled at the item-number level.
- Historical price-adjustment data is kept separate from purchase and return data.
- SideStore installation remains subject to Apple's free developer-account restrictions.

---

# Releases

This repository is the public distribution repository for CostcoTracker.

It contains:

```text
README.md
icon.png
source.json
```

GitHub Releases contain the prebuilt:

```text
CostcoTracker.ipa
```

New releases are published automatically from the private development repository.

Older releases may remain available for version history.

The application source code is maintained separately and is not currently open source.

---

# Availability

CostcoTracker is currently a personal project developed primarily for my own use.

Prebuilt IPA releases are publicly available through this SideStore source for anyone who would like to use the app.

The source code is not currently distributed as an open-source project.

The app is provided **as-is**, without warranty or guarantee of continued support, compatibility, availability, or fitness for a particular purpose.

---

# Disclaimer

Costco, Costco Wholesale, and related marks are trademarks of Costco Wholesale Corporation.

CostcoTracker is an independent, unofficial project. It is not affiliated with, endorsed by, sponsored by, or maintained by Costco Wholesale Corporation.

CostcoTracker does not represent Costco's policies, systems, guarantees, or official eligibility determinations.

Users should independently verify:
- price-adjustment eligibility;
- return eligibility;
- receipt information;
- current Costco policies;

before acting on information shown by the app.
