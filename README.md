# UOCIS322 - Project 1 #

This project will get you started with creating a simple webpage server.

## Installing
 
To install this project, simply fork and clone it, then add your own credentials file. Additionally, you can add your own folder structure of files to serve. If you want to keep the contents of your website private, simply add your docroot folder to your gitignore.

## Serving / Stopping

To serve this project, use the 'make start' command. To stop serving, use the 'make stop' command. The commands 'make clean' and 'make veryclean' will deal with handling cleanup. If, like me, you're having a problem with the 'make stop' command not completely killing the process, and you are working on linux, I recommend the 'fuser -k 5000/tcp' command, where 5000 is replaced with whatever port you have this running on.

## Problem solutions

To make file locations available to the respond function, I created a global variable named "DOCROOT", then assigned to it the value of options.DOCROOT in main(). I identified that the suffix of requests was always in parts\[1]. Error checking was simply "if 'x' in 'z': error respond" where x was the illegal characters we were given, and z was parts\[1]. I used an OS import to check if files existed, and if they did, opened, joined, and served them to the caller. If they did not I served the not_found error message, along with a small string of header to let the user know it could not be found. There is an easter egg you can find, currently, if you try to access with the /cat suffix.

### Authors

Files created by: Michal Young, Ram Durairajan.

Updated and completed by: Tammas Hicks
