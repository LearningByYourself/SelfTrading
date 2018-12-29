# SelfTrading
Fun project for self trading.
## Logging
We use log4j2 as our logging system.

####How to log 
Add
` private static Logger log = LogManager.getLogger();` 
to your class.

The logging framework support log hierarchy.

**FATAL**: the app (or at the very least a thread) is about to die horribly. This is where the info explaining why that's happening goes.

**ERROR**: something that the app's doing that it should not. This isn't a user error ('invalid search query'); it's an assertion failure, network problem, etc etc., probably one that is going to abort the current operation

**WARN**: something that's concerning but not causing the operation to abort; # of connections in the DB pool getting low, an unusual-but-expected timeout in an operation, etc. I often think of 'WARN' as something that's useful in aggregate; e.g. grep, group, and count them to get a picture of what's affecting the system health

**INFO**: Normal logging that's part of the normal operation of the app; diagnostic stuff so you can go back and say 'how often did this broad-level operation happen?', or 'how did the user's data get into this state?'

**DEBUG**: Off in production, on while debugging/developing, able to be turned on for debugging specific unexpected problems. This is where you might log detailed information about key method parameters or other information that is useful for finding likely problems in specific 'problematic' areas of the code.

**TRACE**: "Seriously, WTF is going on here?!?! I need to log every single statement I execute to find this @#$@ing memory corruption bug before I go insane". usually used when you want to debug everything in specific component  