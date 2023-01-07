# bash_server_backup

> Update: 1-7-23
> As you can probably tell, this project is on the backburner for me (for now, at least). I have been doing some scripting in my spare time for some other things though, so hopefully I'll get around to actually getting (at least a rudimentary version of) this project up and running some time, however, at least for now, I don't have any concrete plans to come back to this project. I do have several ideas as for how to implement it, though--I'm just working on some other projects though, and (sadly), I don't exactly have the time/energy to work on 951573 different projects at the same time, lol. Anyways, if anyone's got any questions or comments or anything, I'm always happy to discuss this sorta stuff (as you can probably tell, I'm a bit of a nerd, haha).

Bash script to automatically keep updated backups of my main computer on my server. 

Probably not gonna get a ton of work done on this very soon (due to time constraints with school/work), but I do plan to finish this.

**The general idea:**
I plan to set up a script to automatically backup any data as soon as there is a save or a deletion on my hard drive. 

**How?:**
The plan, at least for now, is to set up a daemon that keeps an eye out for any time data is created, updated, or deleted on my main machine; from there, send the pertaining info to my home file server for updated backups of my laptop drive. 

**Dev notes:**
- figure out how to monitor all changes (even the smallest ones) on a file system, whether by monitoring whenever there is a command sent to the file system to create, update, or delete a file, or via some other method
- use the info from the previous bullet point; send it to the file server in the backup directory(or directories) as soon as the change is made (if connected to internet), so that it can run in the background and not cause much issue, since each change is automatically updated and sent to the server (likely via ssh or sftp)
- if offline, create a local (client-side) "buffer" directory (within the parent directory for the program) to keep tabs on all changes *(not copies, but references to which files were changed, or something along those lines)* and upon connection to the internet, upload them to the server (or present the user with some options as to their preferred method of uploading, so that the internet isn't constantly bogged down as soon as the user connects after being offline)
- use bash for this, at least for now. keeps things simple and tidy, especially considering the versatility of bash scripting. maybe some time make a powershell equivalent, since both are very good for keeping tabs on the operating system as it is running, and therefore are quite likely to be very efficient (and relatively simple) to use.
- if you want, upon further completion of all of this, maybe make a new version with a GUI for those who aren't very "techy" (i guess, lol), and set it up as some free open source software for people to make persistent backups of their computers, only requiring a computer running linux/windows and read/write access to a server-based file system. this way, people won't really have to depend on paid services for this sorta thing, since they really don't need to if they have their own server (or, even a local computer they can set up as a file server via *relatively* simple instructions). 
