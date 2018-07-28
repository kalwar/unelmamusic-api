# unelmamusic-api
api for music sharing platform that allows anyone to create, listen and share music

DEVELOPERS
Our API allows you to retrieve informations from our website via GET request and supports the following query parameters: 

Name	Meaning	Description
t (required)	Query type.	This parameter specify the type of the query, u is for profile informations, t is for tracks informations.
q (required)	Requested username.	The t parameter supports two values:
u = username [returns basic profile informations containing the following]
id = returns the unique user id
username = returns the username
first_name = returns the first name
last_name = returns the last bame
website = returns the website
country = returns the country
city = returns the city
image = returns the profile avatar image
cover = returns the profile cover image
t = username [returns a list of latest 20 tracks uploaded by a user containing the following]
id = returns the unique track id
by = returns the unique user id
title = returns the track title
description = returns the description of the track
art = returns the track artwork image
tag = returns the tag list
buy = returns the purchase url
record = returns the record label
release = returns the release date
license = returns the license type
time = returns the date time when was published
likes = returns the number of likes
views = returns the number of views (times played)


Examples of requests:

For profile information of a user: 
https://www.unelmamusic.com/api.php?t=u&q=USERNAME 

For a list of latest 20 tracks uploaded by a user: 
https://www.unelmamusic.com/api.php?t=t&q=USERNAME 


An example of json decoding would be the following PHP code: 

<?php
header('Content-Type: text/plain; charset=utf-8;'); 
$file = file_get_contents("https://www.unelmamusic.com/api.php?t=t&q=USERNAME");
print_r(json_decode($file));
?>
