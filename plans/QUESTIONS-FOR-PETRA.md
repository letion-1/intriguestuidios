# Critical Questions for Petra

Before proceeding with implementation, I need answers to these questions to ensure the system meets your exact needs.

## 1. Date Range Display Format ⭐ CRITICAL

How should the master calendar display dates?

**Option A: Weekly Rows (Recommended)**
- Each row represents one week (e.g., "2026-07-04 to 2026-07-11")
- ~52 rows for the entire year
- Matches typical yacht charter periods (Saturday to Saturday)
- Easier to scan visually

**Option B: Daily Rows**
- Each row represents one day (e.g., "2026-07-04")
- 365 rows for the entire year
- More granular but harder to read
- Better for day-by-day tracking

**Option C: Custom Charter Periods**
- Rows match your actual charter periods
- Could be 7-day, 10-day, or 14-day periods
- Most accurate but requires defining all periods

**Your Answer:** _________________

## 2. Complete Yacht List ⭐ CRITICAL

Please provide the complete list of yacht names that should appear as columns in the master calendar.

From the links provided, I can see:
- Angelica (from ViewYacht)
- Saint Luca (from Dropbox folder)
- Others from booking lists...

**Your Answer:**
1. _________________
2. _________________
3. _________________
4. _________________
5. _________________
(Add more as needed)

## 3. Update Frequency

How often should the automation run to refresh the master calendar?

**Option A: Daily (Recommended)**
- Runs once per day (e.g., 6:00 AM)
- Fresh data every morning
- ~28,500 Make.com operations/month

**Option B: Hourly**
- Runs every hour
- Near real-time updates
- ~700,000 operations/month (expensive)

**Option C: Weekly**
- Runs once per week
- Less frequent updates
- ~4,000 operations/month (economical)

**Option D: On-Demand**
- Manual trigger only
- Run when needed
- Variable operations

**Your Answer:** _________________

## 4. Output Location ⭐ CRITICAL

Where should the master calendar be created?

**Option A: New Google Sheet**
- Create a fresh sheet for this purpose
- Clean start
- I'll create it during setup

**Option B: Existing Google Sheet**
- Add to an existing sheet you already use
- Please provide the URL: _________________

**Option C: Specific Dropbox Location**
- Save as Excel file in Dropbox
- Please provide the folder path: _________________

**Your Answer:** _________________

## 5. Access Permissions ⭐ CRITICAL

Do you have the necessary access to all data sources?

**Dropbox Files:**
- [ ] I have access to `/Booking-list-2026.xlsx`
- [ ] I have access to `/Saint Luca/Saint Luca - booking2026.xlsx`
- [ ] I can generate a Dropbox access token for Make.com

**Google Sheets:**
- [ ] I have EDIT access to sheet `1Tfz1IPfd_e-I97LQKeQ6qUKs9zrlJ1TuqOa1aSlz9KM`
- [ ] I have EDIT access to sheet `1qrcGvth_FGTqQQTJGNWzQ6EkWBudFwsX`

**Google Docs:**
- [ ] I have access to document `1NhdYhkkzNLShxrgCfasAXJ_GShn8Lkjd`

**Web Pages:**
- [ ] ViewYacht page is publicly accessible (no login required)
- [ ] Aboard Yachting page is publicly accessible (no login required)

**Your Answer:** Check all that apply above, or note any access issues: _________________

## 6. Conflict Resolution Priority

When the same yacht appears booked in multiple sources for the same dates, which source should be trusted?

**Suggested Priority Order:**
1. Owner's direct booking list (Dropbox files) - HIGHEST PRIORITY
2. Your consolidated Google Sheets
3. Google Docs
4. Web pages (ViewYacht, Aboard Yachting) - LOWEST PRIORITY

**Your Answer:** Do you agree with this priority? If not, please specify: _________________

## 7. Historical Data

Do you need to see past bookings, or only current and future bookings?

**Option A: Future Only (Recommended)**
- Only show bookings from today onwards
- Cleaner, more relevant
- Smaller dataset

**Option B: Include Past**
- Show all bookings for 2026
- Historical reference
- Larger dataset

**Your Answer:** _________________

## 8. Additional Data Fields

Besides embarkation and disembarkation ports, do you need any other information in the master calendar?

Possible additional fields:
- [ ] Guest names
- [ ] Booking reference numbers
- [ ] Charter price
- [ ] Number of guests
- [ ] Special requirements/notes
- [ ] Booking status (confirmed/tentative/option)
- [ ] Agent/broker name

**Your Answer:** Check all that apply, or specify others: _________________

## 9. Time Zone

What time zone should be used for dates and execution times?

**Your Answer:** _________________ (e.g., UTC, Europe/Zagreb, Europe/Athens)

## 10. Notification Preferences

How should you be notified about:

**Successful Execution:**
- [ ] Email notification
- [ ] No notification (check manually)
- [ ] Slack notification
- [ ] Other: _________________

**Errors/Failures:**
- [ ] Email notification (recommended)
- [ ] SMS notification
- [ ] Slack notification
- [ ] Other: _________________

**Booking Conflicts Detected:**
- [ ] Email notification
- [ ] Log only (check manually)
- [ ] Slack notification
- [ ] Other: _________________

**Your Answer:** Check all that apply above

## 11. Budget Considerations

Make.com pricing is based on operations used:

**Estimated Usage:**
- Daily updates: ~28,500 operations/month
- Required plan: Pro ($29/month for 40,000 operations)

**Your Answer:**
- [ ] Budget approved for Pro plan
- [ ] Need to reduce frequency to fit free tier (10,000 ops/month)
- [ ] Need cost optimization suggestions

## 12. Data Source Formats

This is important: Can you provide sample data or screenshots from each source showing the actual format?

This will help me build accurate parsers. Specifically:
- How are dates formatted in each source?
- Where are yacht names located (columns, rows, headers)?
- How are embarkation/disembarkation ports indicated?
- Are there any special formatting or merged cells?

**Your Answer:**
- [ ] I can provide sample screenshots
- [ ] I can share sample data files
- [ ] I can grant temporary access for inspection
- [ ] I'll describe the format: _________________

## 13. Testing & Validation

Before going live, would you like to:

**Your Answer:**
- [ ] Test with a small subset of data first
- [ ] Run in parallel with manual process for validation period
- [ ] Go live immediately after testing
- [ ] Other: _________________

## 14. Maintenance & Support

Who will maintain this system after implementation?

**Your Answer:**
- [ ] I will maintain it myself (need training)
- [ ] You will provide ongoing support
- [ ] We'll need a handoff plan
- [ ] Other: _________________

---

## Next Steps After Receiving Answers

Once you provide answers to these questions, I will:

1. ✅ Finalize the technical architecture
2. ✅ Create detailed data mapping specifications
3. ✅ Build and test the Make.com scenarios
4. ✅ Set up the master calendar with your preferences
5. ✅ Test with your actual data
6. ✅ Deploy the automation
7. ✅ Provide training and documentation

---

**Please reply with answers to these questions, and I'll proceed with the implementation plan!**

**Priority Questions:** 1, 2, 4, 5, 12 are the most critical for starting implementation.
