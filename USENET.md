# USENET
## slrn ( + slrnpull + slrnface)

### 1. Create slrn.rc:
* set username "desired_username"
* set hostname "desired_hostname.invalid"
* set replyto "some_name <email@example.com>"
* charset display utf8
* charset outgoing utf8
* setkey group "set_prefix_argument(4); () = select_group();" " "

### 2. Set $NNTPSERVER to usenet provider (set in config file):
* NNTPSERVER='server_name' && export NNTPSERVER

### 3. Set $EDITOR to preferred text editor (set in slrn.rc file):
set editor_command "vim '+set tw=72' +%d '%s'"

### 4. Create .jnewsrc

### 5. slrn --create

### 6. download a list of newsgroups slrn -d
