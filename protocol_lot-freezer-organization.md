# Instructions for Student Workers

## Part A — Jars (“Lots”) in Boxes → organize by **family**

**Goal:** Each box contains jars from a single fish family (Smithsonian/USNM system). There may be multiple boxes per family.

### 0) Safety & setup (5–10 min)

* Wear nitrile gloves and safety glasses; some jars may have formalin residue or strong ethanol. The TH 214 lab is well ventilated.
* Clear a benchtop and lay down absorbent pads or paper towels.
* Gather supplies: permanent lab markers (ethanol-insoluble), blue painter’s tape, pre-printed box labels, phone/camera, and the **[lot audit template](lot_audit_template.csv)**.
* Keep lids hand-tight—do **not** re-seal with excessive force.

### 1) Stage one box at a time

* Bring one mixed box to a benchtop. Don’t spread multiple boxes at once.
* For each jar (1 "lot” = 1 jar), locate the **species code** on the jar label. Use the **[species code decoder](species_code_decoder.csv)** to get the scientific name and family.
* If the jar label is smudged or missing the code:

  * Check for any secondary ID on the label (lot number, species name).
  * If still uncertain, place jar in a **“Needs ID”** area and record it on the template with notes.

### 2) Sort jars by family on the benchtop

* Make family piles (e.g., **LUTJANIDAE**, **GOBIIDAE**, etc.). Confirm by decoding the species code.
* As piles grow large, start packing into **family-dedicated boxes**:

  * Write on two adjacent box faces: **FAMILY NAME – USNM Family Code – Box X of Y** (leave Y blank until the end).
  * Add a removable box card inside with the same info.

> Use the Smithsonian/USNM family codes for consistency (e.g., LUTJANIDAE code 185; GOBIIDAE 255). Refer to the provided **Family Codes for USNM Fish Families** list. 

### 3) Log as you go (Lot Audit Template)

For every jar moved into a family box, enter:

* `box_id` (e.g., **LUTJANIDAE-001**), `family`, **USNM family code**, `lot_id` (if present), `species_code`, `scientific_name`, `n_specimens` (estimate if needed), `preservative` (EtOH/Formalin/Unknown), `jar_size_ml`, `condition_notes` (label legible? fluid low? broken stopper?), `photo_filename` (take 1 label + 1 jar photo), `verified_against_lot_sheet` (Y/N), `initialed_by`, and `date`.

[The lot Sheet Is Located Here](https://github.com/philippinespire/database_albatross_recollections/tree/main/db_files/lots_sheets)

**Tip:** If a lot contains a species not matching the jar label/species_code, do **not** split specimens. Flag the lot as **“label/content mismatch”** in `condition_notes`.

### 4) What to do with outliers

* **Unknown family** → place in a temporary **“Unknown family”** box; list each entry with detailed notes.
* **Damaged/Leaking** → place jar in a secondary container (zip bag), note it, and alert supervisor.
* **Duplicates** (exact same lot found twice) → keep both; note “duplicate?” in `condition_notes` for review.

### 5) Close a family

* When a family’s jars are boxed, count the number of boxes; update every box face: **“Box 1 of N, 2 of N, …”**
* Place completed boxes on the **“Ready for Collections Room”** cart/rack.

### 6) Move into the collapsing-shelf Collections Room

* Shelve by **family (alphabetical)**, then by **box sequence**.
* Record `location_to` on the template (e.g., **Aisle 2, Bay B, Shelf 3**).
* Return the completed **Lot Audit Template CSV** for that family to the master tracking folder.

---

## Part B — Freezers (Tissues & DNA extracts)

**Goal:** Produce a **complete, location-aware inventory** and physically organize by sample type, then family, while keeping **all non-collection samples** clearly separated.

### 0) Safety & cold-chain discipline

* Wear cryo-gloves for dry ice handling; avoid prolonged open-door time. Work with 1 rack/box out at a time.
* Keep an empty, labeled **“Staging on bench”** cooler with ice/dry ice if needed.

### 1) Define the physical layout scheme (labeling)

* Each freezer gets an ID (e.g., **FZ-01**, **FZ-02**).
* Each freezer has numbered **racks** and each rack has **shelf levels** if applicable.
* Each **cryobox** gets a unique `box_id` (e.g., **FZ-01-R2-B07**).
* Inside the cryobox, use grid positions (e.g., **A1 … H12**).
* Keep **collection** vs **non-collection** boxes **physically separate**, on different shelves **and** with different `box_id` prefixes (e.g., **COL-** vs **MISC-**).

### 2) One box at a time: inventory everything

Using the **Freezer Inventory Template**, record for *each tube/vial*:

* `freezer_id`, `rack`, `box_id`, `position_in_box` (grid).
* `sample_type` (**tissue** or **dna**).
* `sample_id_or_barcode` (transcribe exactly; photograph if ambiguous).
* `species_code` (if present on tube or tray) → use **decoder** to fill `scientific_name`, `family`.
* `collection_era` (write **Contemporary** only if you confirm from lot/species sheets—otherwise leave blank).
* `source_collection_note` (e.g., “not part of Contemporary lot collection”).
* `preservative_or_buffer` (e.g., 95% EtOH, DMSO/salt, lysis buffer, TE).
* For DNA: `concentration_ng_ul_if_dna`, `date_extracted_yyyy_mm_dd` if written on the tube or in the box log.
* `storage_temp_c` (e.g., −80, −20).
* `crossref_lot_id_if_applicable` (if you can confidently match to a jar lot).
* `notes`, `initialed_by`, `date_yyyy_mm_dd`.

**Photos:** Take one photo of the **box map** (lid or printed grid) and one of any handwritten index card; save as `FZ-01-R2-B07_boxphoto.jpg` and reference in `notes`.

### 3) Physical re-organization standard

* **DNA extracts** and **tissues** go to **separate** dedicated racks (or shelves).
* Within each sample type, group boxes by **family** (using USNM family names/codes), then by **species** when practical.
* Mixed boxes are allowed during auditing, but **final state** should be one family per box when possible. If a family is sparse, group multiple species within that family in the same box.
* **Non-collection samples** must keep **MISC-** prefix and stay in their own section; never mix into **COL-** boxes.

### 4) Barcoding (if applicable)

* If barcodes exist, scan and record exactly in `sample_id_or_barcode`.
* If not, affix a pre-printed 2D or Code-128 label to the box **only** (not the tube) during this pass; tube relabeling will be a future, supervised task.

### 5) Linkage to the lot/species database

* Any freezer item confidently tied to a jar lot: fill `crossref_lot_id_if_applicable`.
* If you only know the **species_code**, that’s sufficient for now—leave `lot_id` blank and write a note like “species-level link only.”

### 6) Quality flags

* **Low volume** tissue or **evaporated** DNA? Mark **“At-risk”** in `notes`.
* **Unknown or unreadable** tube? Place at the rightmost column positions (e.g., **H10–H12**) and flag **“Unknown ID”** in notes.
* **Box too mixed** to be useful? Split into multiple family-specific boxes and update `box_id` and positions in the sheet.

### 7) Finalize and store

* Close boxes tightly, return to the original freezer level; record final `box_id` and location.
* Upload the completed **Freezer Inventory Template CSV** to the master tracking folder.

---

## Database & Labeling Conventions (shared for both Parts)

* **Families** use **USNM family names and codes** (e.g., **LUTJANIDAE — 185**, **GOBIIDAE — 255**). Keep this **exact** spelling/coding for all boxes, shelves, and database fields. 
* **Box IDs:**

  * **Lots:** `FAMILY-###` (e.g., `LUTJANIDAE-001`).
  * **Freezers:** `FZ-##-R#-B##` (e.g., `FZ-01-R2-B07`).
* **Photos:** `YYYYMMDD_context_identifier.jpg` (e.g., `20250925_LUTJANIDAE-001_label.jpg`).
* **CSV fields:** do not leave required fields blank; if unknown, write `Unknown`.
* **Audit trail:** every row must have `initialed_by` and `date_yyyy_mm_dd`.

---

## How this ties to your current sheets

* **Lots:** Students will mark `verified_against_lot_sheet = Y` when a jar labeled **Contemporary** in `collection_era` matches your **lot_sheet** entry; otherwise `N` with a short note.
* **Species decoder:** The **species code decoder** I generated from your `species_sheet_onedrive.tsv` lets students quickly translate `species_code` → scientific name (and family where present), which is the key to sorting by USNM family.

If you want, I can also print a **one-page quick-reference** of the most common families in your collection (name + USNM code) for box labeling, and pre-generate **box cards** for the families that show up in your data.

---

## Helper files

* [Download the species code decoder](species_code_decoder.csv) — maps `species_code` → scientific name (+ family when available)
* [Download the lot audit template](lot_audit_template.csv)
* [Download the freezer inventory template](freezer_inventory_template.csv)

