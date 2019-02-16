# Email To Name Python (Extract Names from Email Addresses Using Python v2 or v3).
A simple python script that parses first names and last names from emails (and that's not all folks, an extra script that's a ready to go flask-wrapped web API you can get running in minutes - find this in the "email-to-name-python-flask" folder that you can use to parse names from emails via a convenient web API... And that's not all folks! A docker app that will launch the flask wrapped email to name parsing python script and allow you to have your own email to name web API running in a docker container in minutes - find this in the "email-to-name-dockerized" folder).

# How does this script work?
It's quite simple, the script function takes an email address, example: michaelhoffman@arrivistepr.com, it validates the email with a regex, ensures that the email meets length requirements, it then extracts the username portion "michaelhoffman" from the email string, then the script initializes an empty string and starts iterating through the username, so for example, it'll iterate though:

m
mi
mic
mich
micha
michae
michael

And with each iteration it'll attempt to match the new string against a list of first names, when a match is found, the matched name is added to a possible list of names, then the longest name is picked out of the list and subtracted from the username string, so in our case, the match would be "michael" and this would be subtracted from "michaelhoffman" (the username string), so the first name would be michael and the subtracted part would be "hoffman", the first part would be returned as the first name, and the last part as the last name. This is returned by the script, but... what happens if the email has no first name just a last name, in this case, if the script fails to find a name on the first-pass, it performs a second pass looking for any separators and then extracting the characters after the separator and doing a check so, if you were to input the email: h.michael1988@gmail.com, the script would separate the h and the michael and return you the michael as a name match.

This approach has some inherent flaws, emails that include middle initials in them serve to foil this script and ends up causing error in the last name output, but that's a problem we hope to solve soon.


# Credit & Note
This is a v0.1 of the script and we're sure other coders who're far more skilled, handsome, humble and patient than us have made better scripts for this purpose. But this is our attempt to solve this problem we face at our small company: ArrivistePR, check us out: https://arrivistepr.com/

P.S. Credit to source, the first name list used in this script is mostly derived from: https://github.com/dominictarr/random-name/blob/master/first-names.txt 
