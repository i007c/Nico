# Nico

send air qaulity status to discord.

## Installation

install the requirements

```bash
python -m pip install -r requirements.txt
```

make a `configs.py` file with in app.py dir \
then put your configs in it.

```py

TOKEN = 'your-api.waqi.info-token'

WEBHOOKS = [
    # your webhooks
]

CITIES = [
    {
        # a unique id for each city
        'id': 0,
        'name': 'City Name',
        # use this url https://api.waqi.info/search/?token=your-token&keyword=london
        # in order to find your city uid's
        'identities': [11238, 10788, 11258, 10588],
        # thumbnail is optional
        'thumbnail': 'image url',
    }
]


BASE_DATA = {
    'username': 'Webhooks name',
    'avatar_url': 'url of a picture',
}


AIR_ATTRS = ['p', 'h', 'w', 't', 'co', 'no2', 'so2', 'pm25', 'pm10', 'o3']
ATTR_MAP = {
    'p': 'ðŋ Pressure', 'h': 'ð§ Humidity', 'w': 'ðĻ Wind ', 't': 'ðĄ Temperature',
    'co': 'ð Carbon Monoxide', 'no2': 'ðĶī Nitrogen Dioxide', 'so2': 'ð­ Sulfur Dioxide',
    'pm25': 'PM-2.5', 'pm10': 'PM-10', 'o3': 'ð Ozone'
}


```

next move the services into `/etc/systemd/system/` like this:

```bash
mv services/* /etc/systemd/system/
```

modify your **nico.service** file and your are good to go.

```bash
systemctl start nico.timer
systemctl enable nico.timer
```

## Todos

* [ ] making this app in **C** just for fun.
