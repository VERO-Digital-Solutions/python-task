Hello dear python dev!

This repository is supposed to act as a playground for your submission.
Below, you will find the **Task** definition.
Please make sure to commit and push your code regurarly.

Happy Hacking :computer:

# Task

Write a python script that connects to a remote API, downloads a certrain set of resources and converts them to a formatted excel file.
In particular, the script should:

- Take an input parameter --keys/-k that can receive an arbitrary amount of string arguments
- Request the resources located at `https://api.baubuddy.de/dev/index.php/v1/vehicles/select/active`
- Store them in an appropriate data structure
- Filter out any resources that do not have a value set for `hu` field
- Generate an `.xlsx` file that contains all resources and make sure that:
   - Rows are sorted by response field `gruppe`
   - Columns always contain `rnr` field
   - Only keys that match the input arguments are considered as additional columns (ie. when the script is invoked with `kurzname` and `info`, print two extra columns)
   - The file should be named `vehicles_$current_date_iso_formatted.xlsx`
