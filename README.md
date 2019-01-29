# talkien-events

Repository used by Talkien for fetching data.

## Documentation

You must work on a fork and make a PR to submit any new changes.

### Add an event

In `<root>/events.json`, add an entry with the following structure :

```language=json
  {
    "name": "Event name (ex: Codeur en Seine)",
    "id": "Event id name (ex: codeurs-en-seine-2018) - Must not include space",
    "startDate": "Event start date (ex: 2018-11-22T08:30:00+02:00)",
    "endDate": "Event end date (ex: 2018-11-22T18:00:00+02:00)",
    "address": "Event short address (ex: Kindarena - Palais des sports de Rouen)",
    "fullAddress": "Event long address (ex: 40 rue de Lillebonne , 76000 Rouen)",
    "location": { // GPS coordonates for Google Maps
      "latitude": 49.447966,
      "longitude": 1.063625
    },
    "logo": "URL of the logo of the event",
    "description": "Event short description (ex: Rencontre de codeuses & codeurs à Rouen)",
    "longDescription": "Event long description (ex: Une journée par la communauté pour la communauté. Codeurs en Seine est une journée de conférences gratuite qui se déroule à Rouen, pour découvrir, apprendre et partager autour du monde du développement.)",
    "url": "Event website URL (ex: https://www.codeursenseine.com/2018/)",
    "bookingUrl": "Event booking URL (ex: https://www.codeursenseine.com/2018/inscription)",
    "topics": ["Développement", "Web", "Logiciel"], // Some topics to describe the event
    "colors": ["#0078c5", "#004fa6"] // Two main colors of the event
  }
```

### Add a schedule

You're a brave people. The job is a bit long, but it will be cool when you'll see the result.

You need to create an new file in `<root>/<id-of-your-event>/events.json`. Next, create an entry like that for each talk :

```language=json
  {
    "name": "Talk name (ex: "How to love a pony")",
    "startDate": "Talk start date (ex: 2018-10-18T09:30:00+02:00)",
    "endDate": "Talk end date (ex: 2018-10-18T12:30:00+02:00)",
    "description": "Talk description with \n for a new line. (ex: Octave Klaba, Founder et Chairman d’OVH, et Michel Paulin, directeur général, vous présenteront leur vision stratégique, ainsi que le nouveau plan cloud smart qui redéfinira l’offre cloud d’OVH.\nThe END)",
    "speakers": [ // Optional
      {
        "name": "Speaker firstname and lastname (ex: Octave Klaba)",
        "office": "Speaker office (ex: Founder et Chairman)",
        "company": { // Optional - You can add only the name like that : "company": "OVH"
          "name": "Company name (ex: OVH)",
          "website": "Company URL (ex: https://ovh.com)",
          "logo": "Company logo",
        },
        "social": [ // Optional
          {
            "twitter": "Speaker Twitter (ex: @olesovhcom)",
            "website": "Speaker website (ex: https://ovh.com)"
          }
        ]
      }
    ],
    "lang": "Talk language (optional) (ex: FR_fr - ex: EN_en),
    "location": "Talk location (optional) (ex: Salle 3)",
    "category": "Talk category (optional) (ex: Business)",
    "tags": ["Keynote"] // Talk tags
  },
```

#### Date Format
*YYYY-MM-DDThh:mm:ss.sTZD*
where:
     YYYY = four-digit year
     MM   = two-digit month (01=January, etc.)
     DD   = two-digit day of month (01 through 31)
     hh   = two digits of hour (00 through 23) (am/pm NOT allowed)
     mm   = two digits of minute (00 through 59)
     ss   = two digits of second (00 through 59)
     s    = one or more digits representing a decimal fraction of a second
     TZD  = time zone designator (Z or +hh:mm or -hh:mm)