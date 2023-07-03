# offbeat-revival
attempting to revive our fav playlist

---

## offbeat-revival - where to start

- reading spotify API docs
- planning structure
- python backend or total typescript?
  - scala backend later?? 
- test API calls
- web-server structure
  - one big basic container lets not fuck about
  - hosting?
  - do we even host?? 

---

## data structure for sets of people using the app

| column | description |
|---|---|
| id | int |
| main user | spotify user id |
| playlist users | list of spotify user id |

---


## some reading from spotify docs

✔ when done

1. [web app frontpage tutorial](https://developer.spotify.com/documentation/web-api/howtos/web-app-profile)
2. [current user profile API call](https://developer.spotify.com/documentation/web-api/reference/get-current-users-profile)
3. [auth code flow](https://developer.spotify.com/documentation/web-api/tutorials/code-pkce-flow)
4. [create playlist](https://developer.spotify.com/documentation/web-api/reference/create-playlist)
5. [get users featured playlists](https://developer.spotify.com/documentation/web-api/reference/get-featured-playlists)
6. [upload custom playlist cover](https://developer.spotify.com/documentation/web-api/reference/upload-custom-playlist-cover)
  - using some of the album covers from played songs may be prohibited
7. [users top items](https://developer.spotify.com/documentation/web-api/reference/get-users-top-artists-and-tracks)
8. [users recently played items](https://developer.spotify.com/documentation/web-api/reference/get-recently-played)

---

### example of recently played json response

```json
{
  "href": "string",
  "limit": 0,
  "next": "string",
  "cursors": {
    "after": "string",
    "before": "string"
  },
  "total": 0,
  "items": [
    {
      "track": {
        "album": {
          "album_type": "compilation",
          "total_tracks": 9,
          "available_markets": [
            "CA",
            "BR",
            "IT"
          ],
          "external_urls": {
            "spotify": "string"
          },
          "href": "string",
          "id": "2up3OPMp9Tb4dAKM2erWXQ",
          "images": [
            {
              "url": "https://i.scdn.co/image/ab67616d00001e02ff9ca10b55ce82ae553c8228",
              "height": 300,
              "width": 300
            }
          ],
          "name": "string",
          "release_date": "1981-12",
          "release_date_precision": "year",
          "restrictions": {
            "reason": "market"
          },
          "type": "album",
          "uri": "spotify:album:2up3OPMp9Tb4dAKM2erWXQ",
          "copyrights": [
            {
              "text": "string",
              "type": "string"
            }
          ],
          "external_ids": {
            "isrc": "string",
            "ean": "string",
            "upc": "string"
          },
          "genres": [
            "Egg punk",
            "Noise rock"
          ],
          "label": "string",
          "popularity": 0,
          "album_group": "compilation",
          "artists": [
            {
              "external_urls": {
                "spotify": "string"
              },
              "href": "string",
              "id": "string",
              "name": "string",
              "type": "artist",
              "uri": "string"
            }
          ]
        },
        "artists": [
          {
            "external_urls": {
              "spotify": "string"
            },
            "followers": {
              "href": "string",
              "total": 0
            },
            "genres": [
              "Prog rock",
              "Grunge"
            ],
            "href": "string",
            "id": "string",
            "images": [
              {
                "url": "https://i.scdn.co/image/ab67616d00001e02ff9ca10b55ce82ae553c8228",
                "height": 300,
                "width": 300
              }
            ],
            "name": "string",
            "popularity": 0,
            "type": "artist",
            "uri": "string"
          }
        ],
        "available_markets": [
          "string"
        ],
        "disc_number": 0,
        "duration_ms": 0,
        "explicit": false,
        "external_ids": {
          "isrc": "string",
          "ean": "string",
          "upc": "string"
        },
        "external_urls": {
          "spotify": "string"
        },
        "href": "string",
        "id": "string",
        "is_playable": false,
        "linked_from": {},
        "restrictions": {
          "reason": "string"
        },
        "name": "string",
        "popularity": 0,
        "preview_url": "string",
        "track_number": 0,
        "type": "track",
        "uri": "string",
        "is_local": false
      },
      "played_at": "string",
      "context": {
        "type": "string",
        "href": "string",
        "external_urls": {
          "spotify": "string"
        },
        "uri": "string"
      }
    }
  ]
}
```


### example of my (arfan) user json response

```json
{
  "display_name": "Arfan Arif",
  "external_urls": {
    "spotify": "https://open.spotify.com/user/11137709790"
  },
  "href": "https://api.spotify.com/v1/users/11137709790",
  "id": "11137709790",
  "images": [
    {
      "url": "https://scontent-lcy1-1.xx.fbcdn.net/v/t1.18169-1/1743583_10201581850056351_841295544_n.jpg?stp=c0.1.50.50a_cp0_dst-jpg_p50x50&_nc_cat=109&ccb=1-7&_nc_sid=dbb9e7&_nc_ohc=ndzRwmhw28wAX88i3st&_nc_ht=scontent-lcy1-1.xx&edm=AP4hL3IEAAAA&oh=00_AfCA8Vhg9QD2ru3fKcRadxmzsddT8kc0UHinJzVrivDPcQ&oe=64C9FC44",
      "height": 64,
      "width": 64
    },
    {
      "url": "https://scontent-lcy1-1.xx.fbcdn.net/v/t1.18169-1/1743583_10201581850056351_841295544_n.jpg?stp=c0.5.320.320a_dst-jpg_p320x320&_nc_cat=109&ccb=1-7&_nc_sid=0c64ff&_nc_ohc=ndzRwmhw28wAX88i3st&_nc_ht=scontent-lcy1-1.xx&edm=AP4hL3IEAAAA&oh=00_AfBYMCp0G-hyaZgD74yi_ARzTSnjSABemhkrvhqkNJEVmA&oe=64C9FC44",
      "height": 300,
      "width": 300
    }
  ],
  "type": "user",
  "uri": "spotify:user:11137709790",
  "followers": {
    "href": null,
    "total": 7
  },
  "country": "GB",
  "product": "premium",
  "explicit_content": {
    "filter_enabled": false,
    "filter_locked": false
  },
  "email": "arfan.arif@hotmail.co.uk"
}
```

