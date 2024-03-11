---
tags:
  - Project
  - Lesson
---

In this project, we are going to make a console app for managing song and playlist information. It does not need to have any visual interface, but if you're interested in setting that up, you could look into [using windows forms.](https://learn.microsoft.com/en-us/dotnet/desktop/winforms/getting-started-with-windows-forms?view=netframeworkdesktop-4.8)

Before starting on the project, take a look at some small things that will be useful for formatting print statements [[Printing Strings|here]].

# Project 1

## Model Specifications

- Playlist
	- Playlist Name
	- Can contain any number of songs
	
- Songs have the below attributes
	- Title
	- Artist (The artist name)
	- Album (The album name)
	- Duration (In Seconds)

## Menu Specifications
### Main Menu

Displays a list of playlists, along with some id numbers the user can use to select them. Allow the user to enter a number and select a playlist with the corresponding id. Once selected, display the playlist menu.

Additionally, display a list of commands to available to the user:

 - `exit`
	- Exits the app
- `addplaylist`
	- Displays a menu to create a new playlist and prompts the user for information to create it
- `totalduration` 
	- Displays the sum of all playlist durations currently stored in the system

### Playlist Menu

Displays a list of songs, along with some id numbers the user can use to select them. Allow the user to enter a number and select a song with the corresponding id. Once selected, display the song menu.

Additionally, display a list of commands to available to the user:

- `delete`
	- Deletes the playlist
- `addsong` 
	- Adds a song to the playlist
- `duration` 
	- Prints out the total duration of the playlist (rounded to the nearest minute) 

### Song Menu

Display all attributes stored for the specified song. Additionally, display a list of commands available to the user:

- `changetitle`
	- Allows the user to change the title of a song
- `changeartist`
	- Allows the user to change the artist name of a song
- `changealbum`
	- Allows the user to change the album name of a song
- `changeduration`
	- Allows the user to change the duration of a song
- `delete` 
	- Deletes the selected song