Hello dear python dev!

This repository is supposed to act as a playground for your submission.

Before getting started, please make sure use this repository as a **template** and create your own **public** repository, on which you will commit and push your code regularly. 
Once you are ready, please mail us back the link to your repository. 

Below, you will find the **Task** definition.

Happy Hacking :computer:

# Task

Write a python script that connects to a remote API, downloads a certain set of resources, merges them with local resources, and converts them to a formatted excel file.
In particular, the script should:

- Take an input parameter `-k/--keys` that can receive an arbitrary amount of string arguments
- Take an input parameter `-c/--colored` that receives a boolean flag and defaults to `True`
- Request the resources located at `https://api.baubuddy.de/dev/index.php/v1/vehicles/select/active`
- Additionally, read and parse the locally provided [vehicles.csv](vehicles.csv)
- Store both of them in an appropriate data structure and make sure the result is distinct
- Filter out any resources that do not have a value set for `hu` field
- For each `labelId` in the vehicle's JSON array `labelIds` resolve its `colorCode` using `https://api.baubuddy.de/dev/index.php/v1/labels/{labelId}`
- Generate an `.xlsx` file that contains all resources and make sure that:
   - Rows are sorted by response field `gruppe`
   - Columns always contain `rnr` field
   - Only keys that match the input arguments are considered as additional columns (i.e. when the script is invoked with `kurzname` and `info`, print two extra columns)
   - If `labelIds` are given and at least one `colorCode` could be resolved, use the first `colorCode` to tint the cell's text (if `labelIds` is given in `-k`)
   - If the `-c` flag is `True`, color each row depending on the following logic:
     - If `hu` is not older than 3 months --> green (`#007500`)
     - If `hu` is not older than 12 months --> orange (`#FFA500`)
     - If `hu` is older than 12 months --> red (`#b30000`)
   - The file should be named `vehicles_{current_date_iso_formatted}.xlsx`
