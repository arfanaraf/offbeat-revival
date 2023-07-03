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


## some reading

✔ when done

1. https://developer.spotify.com/documentation/web-api/howtos/web-app-profile
2. https://developer.spotify.com/documentation/web-api/reference/get-current-users-profile
3. more
4. then

---

## example of my (arfan) user json response

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

