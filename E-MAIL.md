# E-MAIL

TODO:
* Set cock.li
* Configure mutt
* Create account.
* Set mutiple accounts
* Send mail
* Send attachment
* To cancel an action in mutt hit CTRL+g
* Use notmuch
* set i2p-bote

## DIFFERENT FORMATS
* MAILDIR = several files
* MBOX = one file for everything

### MUTTRC
Example config with cock.li and gmail. Not quite complete but can work if tweaked.
```
#---------------------------------------
# ~/.mutt/muttrc settings mutt 1.5.20
#---------------------------------------
#
#---------------------------------------
# One-Time Previous Steps
#---------------------------------------
# Generate keys with proper user
# $ gpg --gen-key
#
# Make proper directory with file:
# $ mkdir ~/.mutt && touch ~/.mutt/.passwd
#
# Put the following inside ~/.mutt/.passwd:
# set cock_pass="password"
# set gmail_pass="password"
#
# Encrypt with proper user:
# $ gpg -r USER1 -e ~/.mutt/.passwd
# $ shred ~/.mutt/.passwd
# $ rm -f ~/.mutt/.passwd
#
#---------------------------------------
# Process the password file first (the "|" pipes to Mutt)
#---------------------------------------
#source "gpg -d ~/.mutt/.passwd.gpg |"
#
#---------------------------------------
# Account Hooks
#---------------------------------------
account-hook . 'unset imap_user imap_pass' # unset first!
account-hook 'imaps://mail.cock.li:993/' "\
             set imap_user=USER1@cock.li imap_pass=`cat ~/.mutt/.cock ` " # imap_pass=$my_cock_pass "
#account-hook 'imaps://USER2@imap.gmail.com/' "\
#              set imap_user=USER2 imap_pass=$my_gmail_pass "
#
#----------------------------------------
# Folders, mailboxes and folder hooks
#----------------------------------------
#
# Setup for USER1:
#----------------------------------------
set folder = imaps://mail.cock.li:993/
mailboxes =Inbox =Sent =Junk =Trash
folder-hook 'imaps://mail.cock.li:993' " \
        set     folder=imaps://mail.cock.li:993/ \
                record=+Sent \
                smtp_url=smtps://$imap_user@mail.cock.li:465 \
                signature=~/.mutt/USER1.sig \
                from='USER1 <USER1@cock.li> ' \
                realname='USER1' "
#
#----------------------------------------
# Setup for USER2:
#----------------------------------------
#set folder="imaps://USER2@imap.gmail.com/"
#mailboxes =INBOX =[Gmail]/Drafts =[Gmail]/'Sent Mail' =[Gmail]/Spam
#folder-hook 'imaps://USER2@imap.gmail.com' " \
#        set     folder=imaps://USER2@imap.gmail.com/ \
#                postponed=+[Gmail]/Drafts \
#                record=+[Gmail]/'Sent Mail' \
#                smtp_url=smtps://USER2@smtp.gmail.com \
#                smtp_pass=$my_gmail_pass \
#                signature=~/.mutt/USER2.sig \
#                from='USER2 <USER2@gmail.com> ' \
#                realname='USER2' "
#
#----------------------------------------
# Macros to make life easier
#----------------------------------------
macro index <esc>1 "y1<return><return>" # ESC+1 takes to first INBOX
#macro index <esc>2 "y5<return><return>" # ESC+2 takes to the second
#
#---------------------------------------
# Mail-check preferences
#---------------------------------------
set timeout=60	#Check for mail every minute
set mail_check=5
#
#---------------------------------------
# Set preferred editor
#---------------------------------------
set editor='vim + -c "set textwidth=72" -c "set wrap" -c "set nocp" -c "?^$"'
# EOF
```  
