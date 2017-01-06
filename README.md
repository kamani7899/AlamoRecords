# README

## Alamo Records

Alamo Records is a online store that sells vintage vinyl records. It is built on the [Ruby on Rails](http://www.rubyonrails.org) web framework and consists of the following models:

1. Publisher - a publisher sells albums.
2. Album - albums are sold by publishers and include many songs.
3. Song - a song is recorded onto one album. It is written by one artist.
4. Artist - an artist writes songs.

The relationships between models are represented in the following diagram:

![Alamo Records model diagram](public/alamo_records_diagram.png)

## Candidate Instructions

Fork the repository, prepare the application and complete each of the tasks listed below. Tasks include styling changes, adding functionality, fixing bugs and writing tests. Each task should be committed separately into Git with a commit message that includes the task number and a short summary of the task.

Do not add any additional gems to the application.

Complete as many tasks as you can in four hours and then submit a pull request through Github.

### Tasks

1. On the publishers index page, change the color of the table header row to  `#9B59B6`.
2. On the navigation bar, add a link to the newest album.
3. The albums index page is executing multiple queries. Fix this.
4. In the album model, create a scope called `recent` that takes an argument `n` (the number of albums) and returns only the last `n` albums released during the past 6 months.
5. On the new/edit album pages, replace the publisher text field with a dropdown that displays each publisher's name, city and state.
6. Add code to ensure that when an album is saved, a publisher is required.
7. On the songs index page, add a delete button for each song that, when pressed, deletes the song via ajax and removes the row from the page.
8. In the footer, under the LATEST section, display the 2 most recent albums released.
  1. Use a caching technique to prevent this query from executing every request.
9. On the artist show page, duplicate albums are being displayed in some cases. Fix this.
10. Add a field to the album model that indicates whether or not the album is on sale. Include a UI element that allows this field to be changed.
11. Fix all broken tests and write a test for the delete button you added in task 7.
12. Some users have requested an API so they can access Alamo Record data in JSON format. In as little code as possible, enable this functionality.
13. This is your final task. Alamo Records would like to change the artist index page from a table to a grid of artist profile image links. There are no artist profile images available, however, we can use the https://randomuser.me/ service to request fake user data including profile images. Your solution should meet the following requirements:
  1. The artist index page should display a responsive grid of artist profile images. Use the bootstrap grid columns classes to accomplish this.
  2. The profile images should link to the artist show page.
  3. Initially, the profile images will not exist and a placeholder image should be shown on the artist index page.
  4. Once a user navigates to the artist show page, and if there is no profile image, an api request should be made to https://randomuser.me to request data for a user. Using the data returned, save the image url to a field on the artist model. Subsequent requests to the same artist should not generate an api call. Display the image on the artist show page.