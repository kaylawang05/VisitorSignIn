# VisitorSignIn
## A tool to manager visitor sign in/out logs for Springfield Senior Apartment

## Package release history

| Version | Date | Notes |
|---------|------|-------|
| 0.1.0   | 2021-12-22 | Initial package build |

## What's in it?

- [InitJson.py] (InitJson.py) - A script to initalize the apt.json file for all apartments.
- [updateTenants.py] - Script to add/remove tenant/visitor/car info for an apartment.
- [signInOut.py] - Script to sign in and sign out.
- [backups/] - Directory that stores all the backups of apt.json (not version controlled)
- [logs/] - All the sign in and out records are kept here (not version controlled)
- [apt.json] - this is the main JSON file that has data for all apartments (apt number, tenants, visitors, car info).

## How it works
### Update the apartment data (tenant names, visitor names, car info):
```
$ ./updateTenants.py 
Error: You have to specify an APT number
-----------------------------------------------------------------
Usage: update.py <options>
Options:
    -t, --tenant                 Update tenants
    -v, --vistor                 Update visitor
    -c, --car                    Update visitor's car
    -n NUMBER, --number=NUMBER   Specify the APT number
    -h, --help                   Show help information and exit

E.g.: $ ./updateTenanats.py -t -n 201
```
### Sign in or out:
Singing in and out will write to logs/<today's date> file.
```
$ ./signInOut.py
Are you signing in or signing out? (i for signin, o for sign out, e for exit): i
Your answer is i
Enter APT number, e.g. 305 (e to exit): 201
Apt number is 201
Here are the visitors registered for APT 201:
If the visitor is not on the list, please enter e to go back to the main menu to update the visitors.
 1) Jerry
 2) Eric Wang
Enter the number of the visitor you are signing in, e.g. 1 or 1,2 (a for all, e to exit): 1
Here are the visitors [u'Jerry']
You are singing in at 15:48 for:
Jerry

$ ./signInOut.py
Are you signing in or signing out? (i for signin, o for sign out, e for exit): o
Your answer is o
Enter APT number, e.g. 305 (e to exit): 201
Apt number is 201
Found
You are successfully singed out at 15:49
```


