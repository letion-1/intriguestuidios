# Implementation Checklist - Yacht Booking Consolidation

## Pre-Implementation Requirements

### Access & Permissions
- [ ] Obtain edit access to all Google Sheets
  - Sheet 1: `1Tfz1IPfd_e-I97LQKeQ6qUKs9zrlJ1TuqOa1aSlz9KM`
  - Sheet 2: `1qrcGvth_FGTqQQTJGNWzQ6EkWBudFwsX`
- [ ] Obtain access to Google Doc: `1NhdYhkkzNLShxrgCfasAXJ_GShn8Lkjd`
- [ ] Obtain Dropbox access for:
  - `/Booking-list-2026.xlsx`
  - `/Saint Luca/Saint Luca - booking2026.xlsx`
- [ ] Create or identify target Google Sheet for master calendar
- [ ] Verify access to web pages (check if authentication required)

### Make.com Setup
- [ ] Create Make.com account (Pro plan recommended)
- [ ] Connect Google Workspace (OAuth)
- [ ] Connect Dropbox (OAuth)
- [ ] Create Data Stores:
  - `yacht_bookings_temp`
  - `yacht_directory`
  - `port_directory`
  - `error_log`
  - `conflict_log`

### Information Gathering
- [ ] Get answers to key questions from Petra:
  - Date range granularity (daily/weekly/custom)
  - Complete list of yacht names
  - Update frequency preference
  - Output location (new or existing sheet)
  - Conflict resolution priority
  - Historical data requirements
  - Additional data fields needed

## Phase 1: Data Source Inspection

### Manual Inspection Tasks
- [ ] Download and inspect `Booking-list-2026.xlsx`
  - Document column structure
  - Identify date format
  - Identify yacht name location
  - Identify port columns
  - Note any special formatting
- [ ] Download and inspect `Saint Luca - booking2026.xlsx`
  - Same as above
- [ ] Open and inspect Google Sheet 1
  - Document structure
  - Identify header row
  - Map yacht columns
  - Map date columns
- [ ] Open and inspect Google Sheet 2
  - Same as above
- [ ] Open and inspect Google Doc
  - Check if contains structured booking data
  - Document format if applicable
- [ ] Inspect ViewYacht webpage
  - Identify booking calendar element
  - Document HTML structure
  - Check if data is in table or JavaScript
- [ ] Inspect Aboard Yachting webpage
  - Same as above

### Documentation
- [ ] Create data structure document for each source
- [ ] List all unique yacht names found
- [ ] List all unique port names/abbreviations found
- [ ] Document date format variations

## Phase 2: Mapping Tables

### Yacht Name Mapping
- [ ] Create comprehensive yacht name mapping table
- [ ] Add all variations and aliases
- [ ] Define canonical names
- [ ] Load into `yacht_directory` data store

### Port Name Mapping
- [ ] Create comprehensive port mapping table
- [ ] Add all abbreviations and variations
- [ ] Define canonical names
- [ ] Add country information
- [ ] Load into `port_directory` data store

## Phase 3: Build Source Processors

### Scenario A: Dropbox Excel Processor
- [ ] Create new scenario in Make.com
- [ ] Add Dropbox connection
- [ ] Configure file download modules
- [ ] Add Excel parser modules
- [ ] Build data transformation logic
- [ ] Implement date parsing
- [ ] Implement port normalization
- [ ] Implement yacht name normalization
- [ ] Add data store write modules
- [ ] Add error handling
- [ ] Test with actual files
- [ ] Verify data in data store

### Scenario B: Google Sheets Processor
- [ ] Create new scenario in Make.com
- [ ] Add Google Sheets connection
- [ ] Configure range read modules
- [ ] Build iterator logic
- [ ] Extract yacht names from headers
- [ ] Build data transformation logic
- [ ] Implement date parsing
- [ ] Implement port normalization
- [ ] Implement yacht name normalization
- [ ] Add data store write modules
- [ ] Add error handling
- [ ] Test with actual sheets
- [ ] Verify data in data store

### Scenario C: Google Docs Processor
- [ ] Create new scenario in Make.com
- [ ] Add Google Docs connection
- [ ] Configure document read module
- [ ] Build text parsing logic
- [ ] Extract booking information
- [ ] Build data transformation logic
- [ ] Add data store write modules
- [ ] Add error handling
- [ ] Test with actual document
- [ ] Verify data in data store

### Scenario D: Web Scraper
- [ ] Create new scenario in Make.com
- [ ] Configure HTTP request modules
- [ ] Add HTML parsing logic
- [ ] Build data extraction logic
- [ ] Handle different web page structures
- [ ] Build data transformation logic
- [ ] Add data store write modules
- [ ] Add error handling and retries
- [ ] Test with actual web pages
- [ ] Verify data in data store

## Phase 4: Build Consolidation Engine

### Scenario E: Data Consolidation
- [ ] Create new scenario in Make.com
- [ ] Build date range generator
- [ ] Retrieve unique yacht names
- [ ] Build date-yacht matrix logic
- [ ] Implement booking lookup
- [ ] Implement conflict detection
- [ ] Implement conflict resolution
- [ ] Build master sheet structure
- [ ] Configure Google Sheets write modules
- [ ] Implement conditional formatting
- [ ] Add cleanup logic
- [ ] Test with sample data
- [ ] Verify output in master sheet

## Phase 5: Integration Testing

### End-to-End Testing
- [ ] Run all source processors sequentially
- [ ] Verify data store population
- [ ] Check for data quality issues
- [ ] Run consolidation scenario
- [ ] Verify master calendar output
- [ ] Compare output with source data
- [ ] Test conflict resolution
- [ ] Validate date range logic
- [ ] Check embarkation/disembarkation data
- [ ] Verify formatting

### Edge Case Testing
- [ ] Test with overlapping bookings
- [ ] Test with missing data fields
- [ ] Test with invalid date formats
- [ ] Test with unknown yacht names
- [ ] Test with unknown port names
- [ ] Test with empty sources
- [ ] Test with API failures
- [ ] Test with rate limiting

## Phase 6: Scheduling & Automation

### Setup Automation
- [ ] Configure scenario triggers
- [ ] Set execution schedule
- [ ] Link scenarios in correct order
- [ ] Add delays between scenarios if needed
- [ ] Configure error notifications
- [ ] Set up monitoring alerts
- [ ] Test scheduled execution
- [ ] Verify automatic runs

## Phase 7: Documentation & Training

### Documentation
- [ ] Document scenario configurations
- [ ] Create user guide for master calendar
- [ ] Document troubleshooting steps
- [ ] Create maintenance guide
- [ ] Document data mapping rules
- [ ] Create FAQ document

### Training
- [ ] Train Petra on using master calendar
- [ ] Explain how to read availability
- [ ] Show how to trigger manual runs
- [ ] Explain error notifications
- [ ] Demonstrate conflict resolution
- [ ] Provide support contact information

## Phase 8: Monitoring & Optimization

### Initial Monitoring Period
- [ ] Monitor first week of executions
- [ ] Review error logs daily
- [ ] Check data accuracy
- [ ] Gather user feedback
- [ ] Identify optimization opportunities
- [ ] Make necessary adjustments

### Ongoing Maintenance
- [ ] Set up weekly error log review
- [ ] Schedule monthly accuracy checks
- [ ] Plan quarterly optimization reviews
- [ ] Update mapping tables as needed
- [ ] Adjust parsers for format changes
- [ ] Monitor API usage and costs

## Success Criteria

### Technical Success
- [ ] All 7 sources successfully integrated
- [ ] Data accuracy > 95%
- [ ] Execution success rate > 98%
- [ ] Execution time < 5 minutes
- [ ] Zero data loss incidents

### Business Success
- [ ] Petra can quickly identify available yachts
- [ ] Booking conflicts are detected and resolved
- [ ] Manual data consolidation eliminated
- [ ] Time saved vs manual process
- [ ] User satisfaction with system

## Rollback Plan

### If Issues Arise
- [ ] Document rollback procedure
- [ ] Keep backup of manual process
- [ ] Maintain access to all source data
- [ ] Have manual consolidation template ready
- [ ] Document known issues and workarounds

---

**Document Version:** 1.0  
**Created:** 2026-02-14  
**Status:** Ready for Implementation
