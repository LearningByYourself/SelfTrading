# SelfTrading
Fun project for self trading.
## Logging
We use log4j2 as our logging system.

####How to log 
Add
` private static Logger log = LogManager.getLogger();` 
to your class. The IDE will import the default.

When need to log you use the log object for example _(those methods are overloaded meaning you can use different params use documentation)_:

`log.fatal("message")`

`log.error("message")`

`log.warn("message")`

`log.debug("message")`

`log.trace("message")`

#### Explanation about the logs level from highest to lowest
 
The logging framework support log hierarchy. We will log from DEBUG and above in development when code will be on production INFO/WARN and above.

**FATAL**:
Fatal represents truly catastrophic situations, as far as your application is concerned.  Your application is about to abort to prevent some kind of corruption or serious problem, if possible.  This entry in the log should probably result in someone getting a 3 AM phone call.

**ERROR**:
An error is a serious issue and represents the failure of something important going on in your application.  Unlike FATAL, the application itself isn’t going down the tubes.  Here you’ve got something like dropped database connections or the inability to access a file or service.  This will require someone’s attention probably sooner than later, but the application can limp along.

**WARN**:
Now we’re getting into the grayer area of hypothetical.  You use the WARN log level to indicate that you might have a problem and that you’ve detected an unusual situation.  Maybe you were trying to invoke a service and it failed a couple of times before connecting on an automatic retry.  It’s unexpected and unusual, but no real harm done, and it’s not known whether the issue will persist or recur.  Someone should investigate warnings.

**INFO**:
Finally, we can dial down the stress level.  INFO messages correspond to normal application behavior and milestones.  You probably won’t care too much about these entries during normal operations, but they provide the skeleton of what happened.  A service started or stopped.  You added a new user to the database.  That sort of thing.

**DEBUG**:
With DEBUG, you start to include more granular, diagnostic information.  Here, you’re probably getting into “noisy” territory and furnishing more information than you’d want in normal production situations.  You’re providing detailed diagnostic information for fellow developers, sysadmins, etc.

**TRACE**:
This is really fine-grained information—finer even than DEBUG.  When you’re at this level, you’re basically looking to capture every detail you possibly can about the application’s behavior.  This is likely to swamp your resources in production and is seriously diagnostic.