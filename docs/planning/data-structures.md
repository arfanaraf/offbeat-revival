# Database Design


## Main Users DB 

| column           | description             |
| ---------------- | ----------------------- |
| id               | int                     |
| main user        | spotify user id         |
| playlist users   | list of user ids        |
| users auth creds | list of user creds      |


## Playlist Maker

| column         | description             |
| -------------- | ----------------------- |
| main user      | spotify user id         |
| playlist       | list of  song ids       |


## Old Playlists (store compressed)

| column         | description             |
| -------------- | ----------------------- |
| main user      | spotify user id         |
| date           | YYYYMMDD                |
| playlist       | list of  song ids       |

