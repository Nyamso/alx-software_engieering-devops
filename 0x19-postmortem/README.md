Service unavailability


Incident report for Site Outage

Issue Summary
When was the issue detected

On May 22nd, 2023 from 14:39 PM our organisation’s website was down until late in the evening. Most users experienced a 500 internal server error caused by a misspelt filename in a configuration file.

Root Cause and Resolution

After a small site update was deployed without first being tested, an outage to the site began. When no errors were found in our 'error.log' files we modified our configuration file to allow for more error logging.

How the issue was fixed
With the help of 'strace,' it appeared an accidental filename misspelling triggered errors when the site was requested. The server was attempting to locate the file as normal procedure but failed to find the file ending in ".phpp" when it should be looking for ".php"

After changing this line in the '/var/www/html/wp-settings.php' file, tests succeeded to show the site. A puppet manifest was written and executed across all company servers immediately after to restore service.

Corrective and Preventative Measures 
After a discussion it has been decided we can prevent this in the future by:
- Modifying configuration files for more error logging to quicken response times
- Test before deploying on all servers no matter how small an update. This is only a small incident so we are doing great!
Thanks for your patience and your continued confidence in us.

