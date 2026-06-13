# Updating the Team page (no developer needed)

The **Our Team** page (`staff.html`) is driven by a Google Sheet. Once it is connected, you update who appears on the website simply by editing the spreadsheet. No code, no waiting on anyone.

Until you connect a sheet, the page automatically shows a built-in default roster, so it always looks complete.

---

## One-time setup (about 5 minutes)

### 1. Make the Google Sheet

1. Go to [sheets.google.com](https://sheets.google.com) and create a new spreadsheet (or open an existing one).
2. In the **first row**, type these column headers exactly, one per cell:

   | Name | Role | Bio | Photo | Order | Show |
   | ---- | ---- | --- | ----- | ----- | ---- |

3. Add one row per team member. (You can copy the included `staff-template.csv` as a starting point.)

| Column    | What to put                                                                                       |
| --------- | ------------------------------------------------------------------------------------------------- |
| **Name**  | The person's name, e.g. `Dennis A. Chuck, M.D.`                                                   |
| **Role**  | Their title, e.g. `Ophthalmologist & Eye Surgeon`                                                 |
| **Bio**   | One or two friendly sentences (optional)                                                          |
| **Photo** | A link to a photo, **or** a filename like `assets/dr-chuck.jpg`. Leave blank for an auto initial. |
| **Order** | A number for sorting: `1`, `2`, `3`… Lower numbers show first.                                    |
| **Show**  | `TRUE` to display, `FALSE` to hide someone without deleting their row.                            |

### 2. Publish the sheet to the web

1. In Google Sheets, click **File → Share → Publish to web**.
2. In the dialog, choose:
   - **Link** tab
   - The specific sheet/tab (not "Entire Document" if you have other tabs)
   - Format: **Comma-separated values (.csv)**
3. Click **Publish**, confirm, and **copy the link** it shows you. It looks like:
   `https://docs.google.com/spreadsheets/d/e/2PACX-.../pub?output=csv`

### 3. Connect it to the page

1. Open `staff.html` in a text editor.
2. Find this line near the bottom (inside the `<script>`):

   ```js
   const SHEET_CSV_URL = "";
   ```

3. Paste your link between the quotes:

   ```js
   const SHEET_CSV_URL =
     "https://docs.google.com/spreadsheets/d/e/2PACX-.../pub?output=csv";
   ```

4. Save the file and re-upload it (or commit/push). Done.

---

## After setup: how to make changes

Just edit the Google Sheet:

- **Add someone:** add a new row.
- **Remove someone:** delete the row, or set **Show** to `FALSE` to hide them temporarily.
- **Reorder:** change the **Order** numbers.
- **Update a bio, role, or photo:** edit that cell.

Changes appear on the live website within a few minutes. Google refreshes the published file on a short delay, so it is normal for an edit to take a little while to show up.

---

## Photos: the simplest way

> Important: do **not** insert a picture into the cell with Insert -> Image. Those embedded images do not come through when the sheet is published, so they will not appear on the site. The **Photo** cell needs a _link_ (or a filename), not an inserted picture.

### Easiest for the office: Google Drive (no developer needed)

1. Upload the photo to Google Drive (drag it into [drive.google.com](https://drive.google.com)).
2. Right-click the photo -> **Share** -> under "General access" choose **Anyone with the link** -> **Viewer**.
3. Click **Copy link**.
4. Paste that link straight into the **Photo** cell. That's it.

The page automatically converts a normal Drive share link into a displayable image, so you can paste the link exactly as Google gives it to you. (Make sure the file is set to "Anyone with the link," or it will stay private and not show.)

### Alternative: a file in the website

If you have access to the website's files, drop the image into the `assets/` folder and put its filename in the **Photo** cell, like `assets/jane.jpg`. This gives the sharpest result and the fastest load.

### Tips

- Best results: roughly portrait-shaped photos (taller than wide). The page crops to a consistent 4:5 frame.
- No photo yet? Leave the **Photo** cell blank and the page shows a clean colored tile with the person's first initial, so it still looks finished.
- Any other public image link (for example from the practice's website) also works if it points directly at an image.

---

## Troubleshooting

- **A person isn't showing up:** check that **Show** is `TRUE` and **Name** is filled in.
- **Order looks wrong:** make sure **Order** contains numbers, not text.
- **Nothing changed on the site:** wait a few minutes, then refresh. Google's published-file delay is normal.
- **Page shows the default roster:** that means `SHEET_CSV_URL` is still blank, or the sheet could not be reached. Re-check steps 2 and 3.

Built with D1 Vibe Coding
