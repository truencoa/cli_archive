# TrueNCOA Command Line Interface (CLI)

## Overview

For the latest documentation on the API or to customize this application, see TrueNCOA

The CLI accepts the following arguments as: truencoa.exe filename id key [url] [email address]
* filename (required) - the fully qualified path and name to the input file (CSV, tab-delimited)
* id (required) - the API id or account user name/email address
* key (required) - the API key or account password
* url (optional) - the API endpoint URL - defaults to https://app.truencoa.com/api (production) or http://app.testing.truencoa.com/api (testing)
* download (optional) - automatically download the processed file - defaults to false, the system will automatically send the user the NCOA report and no file will be downloaded, when set to true, the file will be downloaded and you will be charged automatically

`Example: truencoa.exe "d:\myfile.txt" "email@address.com" "Password123$" "http://app.testing.truencoa.com/api/" false`

> NOTE: if you're using a batch (BAT) file to automate the process and store the command-line parameters, and your password contains a percent symbol (%), you need to add an additional percent symbol to make it work.

## Input File
The input file (filename) needs to have the following fields defined:
* individual_id
* individual_full_name
* individual_first_name
* individual_last_name
* address_line_1
* address_line_2
* address_city
* address_state
* address_postal_code

## Payment
You will automatically be charged if the "download" parameter is set to true. If you do not have any credits available, the export file will not be downloaded. You can login to the app at the URL you submitted the file to in order to view your credits.

## Output File
The export file will be written back to the input file folder automatically with the same input file name with ".export.csv" added.

