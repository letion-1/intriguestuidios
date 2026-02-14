# Sample Master Calendar Template

## Overview
This document shows what the final master calendar will look like with sample data.

## Master Calendar Structure

### Sheet: "Yacht Availability 2026"

| Date Range | Angelica | Saint Luca | Yacht 3 | Yacht 4 | Yacht 5 |
|------------|----------|------------|---------|---------|---------|
| 2026-07-04 to 2026-07-11 | **OCCUPIED**<br>Embark: Split<br>Disembark: Dubrovnik | **AVAILABLE** | **OCCUPIED**<br>Embark: Athens<br>Disembark: Mykonos | **AVAILABLE** | **OCCUPIED**<br>Embark: Venice<br>Disembark: Venice |
| 2026-07-11 to 2026-07-18 | **AVAILABLE** | **OCCUPIED**<br>Embark: Dubrovnik<br>Disembark: Split | **AVAILABLE** | **OCCUPIED**<br>Embark: Barcelona<br>Disembark: Palma | **AVAILABLE** |
| 2026-07-18 to 2026-07-25 | **OCCUPIED**<br>Embark: Split<br>Disembark: Split | **AVAILABLE** | **OCCUPIED**<br>Embark: Mykonos<br>Disembark: Santorini | **AVAILABLE** | **OCCUPIED**<br>Embark: Palma<br>Disembark: Ibiza |
| 2026-07-25 to 2026-08-01 | **AVAILABLE** | **OCCUPIED**<br>Embark: Split<br>Disembark: Dubrovnik | **AVAILABLE** | **OCCUPIED**<br>Embark: Nice<br>Disembark: Monaco | **AVAILABLE** |

### Color Coding
- **OCCUPIED cells:** Red background (#FF0000), white text
- **AVAILABLE cells:** Green background (#00FF00), black text
- **TENTATIVE cells:** Yellow background (#FFFF00), black text (if needed)

## Usage Example

**Scenario:** Petra needs to find available yachts for July 4-11, 2026

**Steps:**
1. Look at row "2026-07-04 to 2026-07-11"
2. Scan across columns for green "AVAILABLE" cells
3. Available yachts: Saint Luca, Yacht 4

**Scenario:** Petra needs to know where Angelica embarks on July 18-25

**Steps:**
1. Look at row "2026-07-18 to 2026-07-25"
2. Find Angelica column
3. Cell shows: "OCCUPIED, Embark: Split, Disembark: Split"
4. Answer: Split (round trip)

## Additional Sheets

### Sheet: "Yacht Directory"

| Canonical Name | Aliases | Primary Source | Notes |
|----------------|---------|----------------|-------|
| Angelica | M/Y Angelica, ANGELICA, Angelica | ViewYacht | 40m motor yacht |
| Saint Luca | St. Luca, SAINT LUCA, Saint Luca | Dropbox - Saint Luca folder | 35m sailing yacht |
| Yacht 3 | ... | ... | ... |

### Sheet: "Port Directory"

| Canonical Name | Abbreviations | Country | Region |
|----------------|---------------|---------|--------|
| Split | SPL, Split, Split HR | Croatia | Dalmatia |
| Dubrovnik | DBV, Dubrovnik, Dubrovnik HR | Croatia | Dalmatia |
| Athens | ATH, Athens, Piraeus | Greece | Attica |
| Mykonos | MYK, Mykonos, JMK | Greece | Cyclades |
| Venice | VCE, Venice, Venezia | Italy | Veneto |
| Barcelona | BCN, Barcelona | Spain | Catalonia |
| Palma | PMI, Palma, Palma de Mallorca | Spain | Balearic Islands |
| Ibiza | IBZ, Ibiza, Eivissa | Spain | Balearic Islands |
| Nice | NCE, Nice | France | Côte d'Azur |
| Monaco | MCM, Monaco, Monte Carlo | Monaco | - |
| Santorini | JTR, Santorini, Thira | Greece | Cyclades |

### Sheet: "Data Sources"

| Source Name | Type | URL | Last Sync | Status | Records |
|-------------|------|-----|-----------|--------|---------|
| Dropbox - Booking List 2026 | Excel | dropbox.com/... | 2026-02-14 06:00 | Success | 45 |
| Dropbox - Saint Luca 2026 | Excel | dropbox.com/... | 2026-02-14 06:01 | Success | 23 |
| Google Sheets 1 | Spreadsheet | docs.google.com/... | 2026-02-14 06:02 | Success | 67 |
| Google Sheets 2 | Spreadsheet | docs.google.com/... | 2026-02-14 06:03 | Success | 34 |
| Google Docs | Document | docs.google.com/... | 2026-02-14 06:04 | Success | 12 |
| ViewYacht - Angelica | Web | viewyacht.com/... | 2026-02-14 06:05 | Success | 18 |
| Aboard Yachting | Web | abordayachting.hr/... | 2026-02-14 06:06 | Success | 29 |

### Sheet: "Conflicts Log"

| Timestamp | Yacht Name | Date Range | Conflicting Sources | Resolution | Status |
|-----------|------------|------------|---------------------|------------|--------|
| 2026-02-14 06:03 | Angelica | 2026-07-04 to 2026-07-11 | Dropbox-Booking-list-2026, ViewYacht-Angelica | Used Dropbox (higher priority) | Resolved |
| 2026-02-14 06:04 | Saint Luca | 2026-08-15 to 2026-08-22 | Dropbox-Saint-Luca, GoogleSheets-1 | Used Dropbox (higher priority) | Resolved |

### Sheet: "Execution Log"

| Timestamp | Scenario | Duration | Status | Operations Used | Errors |
|-----------|----------|----------|--------|-----------------|--------|
| 2026-02-14 06:00 | Dropbox Processor | 45s | Success | 87 | 0 |
| 2026-02-14 06:01 | Google Sheets Processor | 62s | Success | 156 | 0 |
| 2026-02-14 06:02 | Google Docs Processor | 23s | Success | 34 | 0 |
| 2026-02-14 06:03 | Web Scraper | 78s | Success | 89 | 0 |
| 2026-02-14 06:04 | Consolidation | 134s | Success | 478 | 0 |
| **Total** | **All Scenarios** | **5m 42s** | **Success** | **844** | **0** |

## Mobile-Friendly View

For viewing on mobile devices, consider creating a simplified view:

### Sheet: "Quick View"

| Week Starting | Available Yachts | Occupied Yachts |
|---------------|------------------|-----------------|
| 2026-07-04 | Saint Luca, Yacht 4 | Angelica (Split→Dubrovnik), Yacht 3 (Athens→Mykonos), Yacht 5 (Venice→Venice) |
| 2026-07-11 | Angelica, Yacht 3, Yacht 5 | Saint Luca (Dubrovnik→Split), Yacht 4 (Barcelona→Palma) |
| 2026-07-18 | Saint Luca, Yacht 4 | Angelica (Split→Split), Yacht 3 (Mykonos→Santorini), Yacht 5 (Palma→Ibiza) |
| 2026-07-25 | Angelica, Yacht 3, Yacht 5 | Saint Luca (Split→Dubrovnik), Yacht 4 (Nice→Monaco) |

## Filtering & Sorting Options

### Recommended Google Sheets Features

1. **Filter Views:**
   - "Available Only" - Show only available yachts
   - "By Region" - Filter by embarkation region
   - "By Month" - Show specific month

2. **Conditional Formatting:**
   - Occupied = Red
   - Available = Green
   - Tentative = Yellow
   - Past dates = Gray

3. **Data Validation:**
   - Dropdown for yacht names
   - Dropdown for ports
   - Date range validation

4. **Formulas:**
   - Count available yachts per week
   - Count bookings per yacht
   - Utilization percentage

## Sample Formulas

### Count Available Yachts for a Date Range
```
=COUNTIF(B2:F2,"AVAILABLE")
```

### Yacht Utilization Percentage
```
=COUNTIF(B:B,"OCCUPIED")/COUNTA(B:B)*100
```

### Next Available Date for Specific Yacht
```
=INDEX(A:A,MATCH("AVAILABLE",B:B,0))
```

## API Access (Future Enhancement)

Consider exposing data via Google Sheets API for:
- Mobile app integration
- Website booking widget
- CRM integration
- Reporting dashboard

---

**Document Version:** 1.0  
**Created:** 2026-02-14  
**Purpose:** Template and example for master calendar output
