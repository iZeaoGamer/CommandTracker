# CommandTracker v1.1

Plugin for PocketMine-MP that logs all player commands and censors commands for inappropriate language. 


## Documentation 

CommandTracker provides system administrators the capability to moderate player behavior, 
ensuring proper community etiquette standards are followed. Administrators can review the 
chronology of commands to identify inappropriate behavior, taking proactive measures to 
promote a safe and fun gaming environment for players of all ages.

Administrators can also configure which commands are evaluated for inappropriate word usage 
to prevent players from receiving an inappropriate message.

System administrators manage CommandTracker from the console, ensuring system policy 
for password obfuscation and command censoring are enforced.

## Commands

From the console: 

* `/track bw-add <word> : Add a word to be censored (ban word).`
* `/track bw-del <word> : Remove a word from being censored (unban word).`
* `/track cc-add <command> : Add a command to be censored (censor command).`
* `/track cc-del <command> : Remove a command from being censored (uncensor command).`
* `/track sp : Toggles password visibility in console log (show password). Applies until reset or server restarted.`

Note: By default banned words with invoke a substring match; thereby, finding various root, 
prefix, and suffix variants.In some cases, this may not be desired; therefore, a complete 
word match can be qualified by adding the word with a preceding backslash "\". The backslash 
will inform the comparison operation to perform a word compare

## Configuration

You can modify the _CommandTracker/config.yml_ file in the _plugins_ directory once the plugin 
has been run at least one time.

| Configuration | Type | Default | Description |
| :---: | :---: | :---: | :--- |
| log-tofile | boolean | false | Redirects tracking log from the console to a file in _CommandTracker/logs_.
| show-passwords | boolean | false | Obfuscate passwords for SimpleAuth's "register" and "login" commands
| commands-censored | string | say,tell | Comma separated list of commands that qualify for censoring.
| commands-ignored | string | empty | Comma separate list of commands to suppress from tracking.
| words-banned | string | empty | Comma separated list of words deemed inappropriate.

## Permissions

| Permission | Default | Description |
| :---: | :---: | :--- |
| commandtracker.commands.track: | false | Only system administrators can manage command tracking configuration.
