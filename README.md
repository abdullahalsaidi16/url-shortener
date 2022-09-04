# URL Shortener Django APP
## Description
The webservice has the following endpoints:

###  `POST /shorten`

The request body will have the following content
```json
{
    "url": "https://www.example.com/",
    "shortcode": "ewx123"
}
```
When no shortcode provided it should create a random shortcode for the
provided url. The shortcode has a length of 6 characters and will contain only
alphanumeric characters or underscores.
Returns http status 201 with the following body:
```json
{
    "shortcode": "ewx123"
}
```

### `GET /<shortcode>`

Returns http status 302 with the Location header containing the url

```json
{
    "created": "2017-05-10T20:45:00.000Z",
    "lastRedirect": "2018-05-16T10:16:24.666Z",
    "redirectCount": 6
}
```
- `created` contains the creation datetime of the shortcode (in ISO8601)
- `lastRedirect` contains the datetime of the last usage of the shortcode (in
ISO8601)
- `redirectCount` indicates the number of times the shortcode has been used




# Start Project with Docker

# Setup Development Enviroment

## Setup Virtual Enviroment
```bash
virtualenv venv --python=python3.8.3
source venv/bin/activate
```
### install the required python packages
```bash
pip install -r requirements.txt
```
### Run server locally
```bash
make local
```

# Running the unit tests