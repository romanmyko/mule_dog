# SpaceX System API #
## Endpoints ##
### Production ###
`http://ua-1185-spacex-system-api.us-e2.cloudhub.io/api/`
### Local ###
`http://0.0.0.0:8081/api/`
## API Endpoints ##
### Get All Cores ###
**GET /cores**

Request

`GET http://ua-1185-spacex-system-api.us-e2.cloudhub.io/api/cores`

Response
```json
[
    {
        "core_serial": "B1049",
        "status": "active",
        "original_launch": "2018-09-10T04:00:00.000Z",
        "missions": [
            {
                "name": "Telstar 18V",
                "flight": 1
            }
        ],
        "details": "First re-flight of block 5.",
        "reuse_count": 1,
        "rtls_attempts": 1,
        "rtls_landings": 1,
        "asds_attempts": 1,
        "asds_landings": 1,
        "water_landing": false
    }
]
```
### Get All Launches ### 
**GET /launches?page=2**

Request

`GET http://ua-1185-spacex-system-api.us-e2.cloudhub.io/api/launches?page=2`

Response

```json
{
    "launches": [
        {
            "flight_number": 110,
            "mission_name": "Starlink 4",
            "launch_date_utc": "2020-01-29T14:06:00.000Z",
            "rocket": {
                "rocket_id": "falcon9",
                "rocket_name": "Falcon 9",
                "rocket_type": "FT"
            },
            "details": "This is the fourth batch of approximately 60 satellites for SpaceX's Starlink broadband network."
        }
    ]
}

```
### Get All Rockets ###
**GET /rockets**

Request

`GET http://ua-1185-spacex-system-api.us-e2.cloudhub.io/api/rockets`

Response
```json
[
    {
        "rocket_id": "falcon1",
        "rocket_name": "Falcon 1",
        "rocket_type": "Merlin A",
        "first_flight": "2006-03-24",
        "active": false,
        "stages": 2,
        "boosters": 0,
        "cost_per_launch": 6700000,
        "success_rate_pct": 40,
        "country": "Republic of the Marshall Islands",
        "company": "SpaceX"
    }
]
```
### Get All Launchpads ###
**GET /launchpads**

Request

`GET http://ua-1185-spacex-system-api.us-e2.cloudhub.io/api/launchpads`

Response
```json
[
    {
        "id": "5e9e4502f509094ba4566f84",
        "name": "CCAFS SLC 40",
        "status": "active",
        "location": {
            "name": "Cape Canaveral",
            "region": "Florida"
        },
        "vehicles_launched": [
            "Falcon 9"
        ],
        "details": "SpaceX primary Falcon 9 launch site. Has been used for ISS and commercial satellite launches."
    }
]
```
### Get All Payloads ### 
**GET /payloads**

Request

`GET http://ua-1185-spacex-system-api.us-e2.cloudhub.io/api/payloads`

Response
```json
[
    {
        "payload_id": "Telkom-4",
        "norad_id": [
            43587
        ],
        "reused": false,
        "customers": [
            "Telkom"
        ],
        "nationality": "Indonesia",
        "manufacturer": "SSL",
        "payload_type": "Satellite",
        "orbit": "GTO",
        "mass_kg": 5800,
        "mass_lbs": 12787.8
    }
]
```
### Get All Capsules ### 

**GET /capsules**

Request

`GET http://ua-1185-spacex-system-api.us-e2.cloudhub.io/api/capsules`

Response

```json
[
    {
        "capsule_serial": "C113",
        "capsule_id": "dragon1",
        "status": "active",
        "original_launch": "2017-06-03T21:07:00.000Z",
        "missions": [
            {
                "name": "CRS-11",
                "flight": 1
            }
        ],
        "landings": 1,
        "type": "Dragon 1.1",
        "details": "Reused capsule for CRS-13",
        "reuse_count": 1
    }
]
```
### Get Launchpad by ID ###

**GET /launchpads/{id}**

Request

`GET http://ua-1185-spacex-system-api.us-e2.cloudhub.io/api/launchpads/5e9e4502f509092b78566f87 `

Response
```json
{
    "id": "5e9e4502f509092b78566f87",
    "name": "CCAFS SLC 40",
    "status": "active",
    "location": {
        "name": "Cape Canaveral",
        "region": "Florida"
    },
    "vehicles_launched": [
        "Falcon 9"
    ],
    "details": "SpaceX primary Falcon 9 launch site. Has been used for ISS and commercial satellite launches."
}
```

### Get Core by ID ###
**GET /cores/{id}**

Request

`GET http://ua-1185-spacex-system-api.us-e2.cloudhub.io/api/cores/5e9e289df35918033d3b2623`

Response
```json
{
    "core_serial": "B1049",
    "status": "active",
    "original_launch": "2018-09-10T04:00:00.000Z",
    "missions": [
        {
            "name": "Telstar 18V",
            "flight": 1
        }
    ],
    "details": "First re-flight of block 5.",
    "reuse_count": 1,
    "rtls_attempts": 1,
    "rtls_landings": 1,
    "asds_attempts": 1,
    "asds_landings": 1,
    "water_landing": false
}
```
### Get Rocket by ID ###

**GET /rockets/{id}**

Request

`GET http://ua-1185-spacex-system-api.us-e2.cloudhub.io/api/rockets/5e9d0d95eda69973a809d1ec`

Response
```json
{
    "rocket_id": "falcon1",
    "rocket_name": "Falcon 1",
    "rocket_type": "Merlin A",
    "first_flight": "2006-03-24",
    "active": false,
    "stages": 2,
    "boosters": 0,
    "cost_per_launch": 6700000,
    "success_rate_pct": 40,
    "country": "Republic of the Marshall Islands",
    "company": "SpaceX"
}
```
### Get Payload by ID ###
**GET /payloads/{id}**

Request

`GET http://ua-1185-spacex-system-api.us-e2.cloudhub.io/api/payloads/5eb0e4b5b6c3bb0006eeb1e1`

Response

```json
{
    "payload_id": "Telkom-4",
    "norad_id": [
        43587
    ],
    "reused": false,
    "customers": [
        "Telkom"
    ],
    "nationality": "Indonesia",
    "manufacturer": "SSL",
    "payload_type": "Satellite",
    "orbit": "GTO",
    "mass_kg": 5800,
    "mass_lbs": 12787.8
}
```

### Get Capsule by ID ###
**GET /capsules/{id}**
Request

`GET http://ua-1185-spacex-system-api.us-e2.cloudhub.io/api/capsules/5e9e2c5bf35918ed873b2664`

Response
```json
{
    "capsule_serial": "C113",
    "capsule_id": "dragon1",
    "status": "active",
    "original_launch": "2017-06-03T21:07:00.000Z",
    "missions": [
        {
            "name": "CRS-11",
            "flight": 1
        }
    ],
    "landings": 1,
    "type": "Dragon 1.1",
    "details": "Reused capsule for CRS-13",
    "reuse_count": 1
}
```
### Get Launch by ID ###
**GET /launches/{id}**
Request

`GET http://ua-1185-spacex-system-api.us-e2.cloudhub.io/api/capsules/5e9e2c5bf35918ed873b2664`

Response
```json
{
    "fairings": {
        "reused": false,
        "recovery_attempt": false,
        "recovered": false,
        "ships": []
    },
    "links": {
        "patch": {
            "small": "https://images2.imgbox.com/f8/27/XwZPEhTJ_o.png",
            "large": "https://images2.imgbox.com/ae/62/D6SZleUG_o.png"
        },
        "reddit": {
            "campaign": null,
            "launch": "http://www.reddit.com/r/spacex/comments/1ndlay",
            "media": null,
            "recovery": null
        },
        "flickr": {
            "small": [],
            "original": []
        },
        "presskit": "https://spaceflightnow.com/falcon9/006/UpgradedF9DemoMission_PressKit.pdf",
        "webcast": "https://www.youtube.com/watch?v=uFefasS6bhc",
        "youtube_id": "uFefasS6bhc",
        "article": "http://www.parabolicarc.com/2013/09/29/falcon-9-launch-payloads-orbit-vandenberg/",
        "wikipedia": "https://en.wikipedia.org/wiki/CASSIOPE"
    },
    "static_fire_date_utc": "2013-09-19T00:00:00.000Z",
    "static_fire_date_unix": 1379548800,
    "net": false,
    "window": 0,
    "rocket": "5e9d0d95eda69973a809d1ec",
    "success": true,
    "failures": [],
    "details": "Commercial mission and first Falcon 9 v1.1 flight, with improved 13-tonne to LEO capacity. Following second-stage separation from the first stage, an attempt was made to perform an ocean touchdown test of the discarded booster vehicle. The test provided good test data on the experiment-its primary objective-but as the booster neared the ocean, aerodynamic forces caused an uncontrollable roll. The center engine, depleted of fuel by centrifugal force, shut down resulting in the impact and destruction of the vehicle.",
    "crew": [],
    "ships": [
        "5ea6ed2d080df4000697c903"
    ],
    "capsules": [],
    "payloads": [
        "5eb0e4bbb6c3bb0006eeb1ee"
    ],
    "launchpad": "5e9e4502f509092b78566f87",
    "flight_number": 11,
    "name": "CASSIOPE",
    "date_utc": "2013-09-29T16:00:00.000Z",
    "date_unix": 1380470400,
    "date_local": "2013-09-29T09:00:00-07:00",
    "date_precision": "hour",
    "upcoming": false,
    "cores": [
        {
            "core": "5e9e289ff359180ae23b262d",
            "flight": 1,
            "gridfins": false,
            "legs": false,
            "reused": false,
            "landing_attempt": true,
            "landing_success": false,
            "landing_type": "Ocean",
            "landpad": null
        }
    ],
    "auto_update": true,
    "tbd": false,
    "launch_library_id": null,
    "id": "5eb87ce1ffd86e000604b334"
}
```
