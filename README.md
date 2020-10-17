# RekonCentinel
<BR><BR>
Cheap "infosec" device called "Rekon Centinel". Rock64v2 1.5GHZ/1GB, Cute little case with an i2c lcd display, and a nice 3A power supply too. Its just a basic python honeytrap with some fake ports open that will trigger an alert if enumeration is performed on the LAN. It also runs nmaps and banner grabs against everything on its attached LAN (daemonized it looks like, not a cron job). They were smart enough to underclock the CPU so it runs cooler. Whoever wrote the code LOVES sqllite, uses a lot of curse words for testing their stuff, and left their root .bash_history/.viminfo behind... sigh, great OPSEC coming from Fort Meyers, FL. Great job.
  
  ![image](https://i.imgur.com/XC2qQCb.gif)
<BR><BR>
Logs and alerts get shipped to their API for storage and webui access; shipped to their side for SMTP stuff as well it looks like, that way messages will pass dmarc/spf checks. Authentication is pretty smart tho, each box cuts its own creds and then creates a new "device" with the /initial URI suffix. There is a seed key for initial setup which means you can probably spin up fake device IDs in their APIs DB. I doubt they are checking device IDs against a master list. But thats a question for another day...
<BR><BR>
OSINT on the box shows it was most likely a single developer who is C-Suite for CIGENT/CPR-Tools. OSINT on Cigent is a winding and twisted road of USAF/DOD contracts and FUD sales. Their main corp CPR-Tools has some interesting data recovery capabilities, interesting reviews though... Delaware corp, of course.
<BR><BR>
Filesystem dump, including their little LUKS encrypted firmware image, are in /payloads on the main site. sysopt.tar.gz has the main juices, fresh squeezed with no redactions. Surprisingly havent found a RAT or any type of persistence on this thing yet (yet, being the operative word, im gonna keep digging because there is weirdness afoot). 
<BR><BR>
If one of these is on your network, remove it now.
<BR><BR>
Ive never done business with or signed into any agreement legal or otherwise with Cigent or CPR-Tools. I also dont have any stake in these companies or anything against them. This is just a fun weekend project. Legal disclaimer, yada yada, dont use this firmware dump for bad stuff, be nice.
  
