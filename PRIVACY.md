# PRIVACY

## KPCLI
Command line password manager, quite intuitive if you know the command line and designed for daily use.

### OUTSIDE KPCLI
* get short help for the command line  
`kpcli --help`
* open kpcli  
`kpcli`
* open an existing database  
`kpcli --kdb /location/of/database.kdb`


### INSIDE KPCLI
* get commands cheatsheet  
`help`
* to create a database for the first time (dont forget to remember the master password you give it!)  
`saveas DATABASE_NAME.kdb`
* create new entry (will ask for information)  
`new`
* to show contents of an entry  
`show ENTRY_NAME`
* to show contents of an entry using its number on the list  
`show ENTRY_NUMBER`
* to show full contents of an entry including the password using its number on the list  
`show -f ENTRY_NUMBER`
* to edit an entry (will ask for information and create new password unless using interactive password setup!)  
`edit ENTRY_NUMBER`
* to copy the username of an entry to the clipboard  
`xu ENTRY_NUMBER`
* to copy the password of an entry to the clipboard  
`xp ENTRY_NUMBER`
* to copy the url of an entry to the clipboard  
`xw ENTRY_NUMBER`
* to clear the clipboard  
`xx`
* to search for an entry  
`find NAME_OR_PATTERN`


## GPG
File encryption.

* generate keys for the first time, will ask for OPTIONAL information and let you decide encryption algorithm  
`gpg --full-gen-key`
* encrypt file for a recipient RECIPIEND@SOMEWHERE.com  
`gpg -r RECIPIEND@SOMEWHERE.com -e file.txt`
* don't forget to delete the original file and overwrite its former memory address  
`shred -u file`
* decrypt file  
`gpg -d file.gpg`
