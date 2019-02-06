# TrueNCOA Command Line Interface (CLI)
The CLI allows you to process files in an automated fashion directly from your computer without needing to manually upload them to the TrueNCOA application.  You can also use this in the sandbox environment when testing your integration with the TrueNCOA application.
> NOTE:  we only support the Windows platform running .NET Framework 4+ (sorry)

## Overview

For the latest documentation on the API or to customize this application, see TrueNCOA https://truencoa.com/api/

The CLI accepts the following arguments as: truencoa.exe filename id key [url] [download]
* filename (required) - the fully qualified path and name to the input file (CSV, tab-delimited)
* id (required) - the API id or account user name/email address
* key (required) - the API key or account password
* url (optional) - the API endpoint URL - defaults to https://app.truencoa.com/api (production) or https://app.testing.truencoa.com/api (testing)
* download (optional) - automatically download the processed file - defaults to false, no file will be downloaded, when set to true, the file will be downloaded and you will be charged automatically

`Example: truencoa.exe "d:\myfile.txt" "email@address.com" "Password123$" "https://app.testing.truencoa.com/api/" false`

> NOTE: if you're using a batch (BAT) file to automate the process and store the command-line parameters, and your password contains a percent symbol (%), you need to add an additional percent symbol to make it work.

## Input File
The input file (filename) needs to have the following fields defined:
* individual_id - your unique id
* individual_first_name - first name
* individual_last_name - last name
* address_line_1 - address line 1 or full street address
* address_line_2 - address line 2 or blank
* address_city_name - city name
* address_state_code - state code, like 'IL'
* address_postal_code - five-digit or full postal code

Optionally, you can include the following fields:
* individual_full_name - only one full name, do not include individual_first_name and individual_last_name when including this
* address_country_code - blank or 'US'

## Payment
You will automatically be charged if the "download" parameter is set to true. If you do not have any credits available, the export file will not be downloaded. You can login to the app at the URL you submitted the file to in order to view your credits.

## Output File
The export file will be written back to the input file folder automatically with the same input file name with ".export.csv" added.

