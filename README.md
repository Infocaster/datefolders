# Datefolders
This package creates Datefolders (year/month(/day)) for the specified doctype for Umbraco 8.2.x+ . For umbraco 7 use v2 and older versions please use v1.4

# Behavior
- When you create a document with doctype "itemDocType", this package will automatically create year/month/day folders for it
- When you edit the "itemDateProperty", the document is automatically moved to the correct year/month/day folder
- Automatically cleans up empty year, month and day folders
- Orders the items in the year, month and dayfolders by "itemDateProperty" with every action

## Configuration
Add these keys/values to your appSettings section in the web.config:

Key: "datefolders:ItemDocType" - the doctype alias to create datefolders for (e.g. "newsItem") - comma separated values are allowed for multiple doctype aliases 

Key: "datefolders:ItemDateProperty" - the property of the itemDocType to read the date from (e.g. "startDate") (don't add this key if you just want to use the document's create date)

Key: "datefolders:DateFolderDocType" - the doctype to use for creating the year/month/day folders (e.g "DateFolder")

Key: "datefolders:CreateDayFolders" - boolean indicating whether or not day folders should be created

Key: "datefolders:OrderByDecending"  - boolean indicating sort order for date folders (default: false)


## Changelog

Version 3.0.0 
- Updated to use umbraco v8.

Version 2.1.2
- Fixed nested date folders.
- Fix to sort

Version 2.1.1
- Fixed cast error when using Date picker with DB type date.

Version 2.1
- Removed legacy configuration settings
- Added datefolders:OrderByDecending
- Implemented fix for 'Publish At' given by - Wayne Godfrey
- Refactored to reduce code complexity

Version 2.0.1
- Fix to order by child name

Version 2.0
- Updated to use umbraco v6 api.
- Fixed ordering to handle non date folders.

Version 1.4
- Removed Threading (Threading can cause the back-end to be out-of-sync, therefore removed)
- Changed configuration keys, added prefix (legacy still works)
- Added day folders feature (configurable, off by default)
- Fixed silly order by hard-coded propertyAlias bug

Version 1.3
- Better exception handling (speechbubble)
- Exception get's handled when the datefoler document type doesn't exist
- Month folders are now named with a leading zero if the month number is a single number (01, 02 etc.)
- Exception get's handled when a date item is created under the 'Content' root node

Version 1.2
- Support for multiple docTypes (comma separated)

Version 1.1
- Tree get's synced automatically