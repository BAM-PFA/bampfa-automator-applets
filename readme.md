# BAMPFA Automator Applets

This is a collection of OSX Automator applets \(and related/dependent things like OSX services\) that are used for various purposes at BAMPFA, including Drupal data entry. You can download the zipped apps or directories that contain the app and dependent services.

## Data entry applets

----

### Auto-tab-year:

This is intended to aid in the entry of beginning/ending dates for the BAMPFA Drupal CMS. For films in particular, dates must be entered in the format YYYY-MM-DD, with the release year of a film represented as YYYY-01-01 \[through\] YYYY-12-31, entered into two separate fields. For example, *Bladerunner* was released in 1982, so its beginning/ending dates would be entered as:
Beginning date: 1982-01-01  Ending date: 1982-12-31
 
#### usage
This applet asks you for a year, then asks you to click into the first \(earliest\) date field, then to click "continue." The full date range is pasted into the appropriate date fields for you.

Recommended installation: 
1) Create a folder in your `Applications` folder for Automator apps. Copy the app `auto-tab-year` into the folder.
2) Copy the workflow `launch-year` into `[USER]>Library>Services`.
3) Open `System Preferences>Keyboard>Shortcuts>Services`. You should see `launch-year` under General. Click into the shortcut column and type in your preferred shrotcut. I used `⌘F1` . 
4) Press your shortcut to test it out.

You could also just use this as a standalone applet that you double click whenever you need to access the date range, but that defeats the time-saving nature of this shortcut.


### Plain Text Paster

This is similar to the Date Range paster, but has more general application. You can copy formatted text to the clipboard and paste plain text with the formatting stripped. I find myself using this all the time.

#### usage

Copy formatted text. Put your cursor somewhere nice and paste plain text. 

Recommended installation:

1) Create a folder in your `Applications` folder for Automator apps. Copy the app `plain-text` into the folder.
2) Copy the workflow `do-pain-text` into `[USER]>Library>Services`.
3) Open `System Preferences>Keyboard>Shortcuts>Services`. You should see `do-pain-text` under General. Click into the shortcut column and type in your preferred shrotcut. I used `⌘⇧V `.  \(Command-Shift-v\)
4) Press your shortcut to test it out.

## Miscellaneous other applets
-----

### Clean-piction-names

This app takes a directory of images downloaded from Piction and removes extraneous text added to the filename by the DAMS. 

#### usage

This is a simple droplet. Put all the images with dirty Piction filenames into a folder. Drop the folder onto the applet and confirm that you want to clean the filenames. You can keep the droplet on your Desktop, or soemwhere else handy. *This app uses a less than efficient script, so give it a minute to do its thing, especially if you have a lot of images to rename*.

When images are downloaded from Piction via the "Download Lightbox" function, some extra text is added to the filename as part of the system's unique ID tracking. Full sized downloads follow the format:

**d\[4-digits\]u\[8-digits\]filename.extension**

example : **d7566u34475667ORIGINAL-FILENAME_o4.jpg** 

For derivative images, there is an additional _o\[1-digit\].

It is unclear what the 4-digit number following the "d" is. The 8-digit number following the "u" is the Piction UMO ID \(unique system ID for the asset\). The single digit following "_o" is the Piction derivative level indicator.

### Cinefiles backup log

This is a script to create a .CSV file that logs all the `.jpg`, `.tif`, or `.tiff` images in a specified directory. It logs the following information: File Name, File Size, MIME Type, Last Modified, File Path. Ultimately, this should help us keep track of images should we ever need to reconnect any of our media. Which has happened before.


#### usage 

This is currently a droplet, where we will drag and drop our Uploaded Images backup folder on a DROBO. the .CSV file is output with the following file name format: `cinefiles-backup-log_2016-03-07.csv`. 

#### next steps: 

This should really be run automatically on a weekly or monthly basis, with some means to check if it is running properly. 