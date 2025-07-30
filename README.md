# Geocoding-Pipeline

** Note: public version. This will not run, since I've removed some files containing personal info. **

This is the geocoding pipeline I developed for the purpose of mapping event attendees (and their respective organizations) to their personal and work political districts. Attendees had their home address and work address geocoded, with the final result being a spreadsheet of house and senate districts of attendees.

The result of this pipeline is added to the clients master spreadsheet. It's built so that whenever the client hosts a new event, I can just alter the inputs and send them the final excel output to add to their master spreadsheet. 


# Pipeline breakdown

1) Web scraping
	-- scraping-reps.ipynb
	-- There wasn't an easily accessible csv of PA representatives, so I built a simple scraper
	-- Scraper outputs two CSVs, 'PA house reps' and 'PA senate reps' containing only relevant info
	-- only needs to be run if there's a new election

2) Geocoding
	-- parsing-geocoding.ipynb
	-- reading and formatting source excel doc into dataframe
	-- geocoding personal and work addresses
	-- mapping personal and work addresses to senate and house districts
	-- outputs two CSVs, 'home districts' and 'org districts'

3) Joining CSVs in excel
	-- parsed event 4-1-25.xlsm
	-- new excel book from CSVs 'home districts' and 'org districts'
	-- Using VBA, 'PA house reps' and PA senate reps' sheets matched to attendees list
	

Files removed for privacy:
	-- home districts.csv (names + addresses)
	-- event_2181933_attendees 3.31 6.32 PM.xlsx (source excel doc, names + addresses)

Cell outputs in 'parsing-geocoding' containing personal info have been cleared. I also cleared some outputs just to reduce the bloat a bit, but left a handful so you can see what things look like. 
