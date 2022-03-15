# Fask Ovunque

From a project by [Nick Sawhney]("https://github.com/nicksawhney/bernie-sits/"), modified code published according to the [GNU Affero General Public License](https://www.gnu.org/licenses/agpl-3.0.en.html).

[![Deploy](https://www.herokucdn.com/deploy/button.svg)](https://heroku.com/deploy)

## Install 

First, create a python virtual environment, and install all of the depenedencies. 
```
python3 -m venv ve
source ve/bin/activate
pip install -r requirements.txt
```

Next, create a google cloud platform project with Street View Static API access (you will need a credit card to set this up)

https://console.cloud.google.com/apis/library/street-view-image-backend.googleapis.com

Set the following environment variables by adding the following lines to your `.bash_profile`, `.zshrc`, etc:
```
export API_URL='https://maps.googleapis.com/maps/api/streetview'
export KEY='YOUR-MAPS-STREETVIEW-KEY'
export SECRET='YOUR-GOOGLE-SECRET'
```

You might want to rename the variables to not conflict with existing ones.

## Running 

To run the web application locally
```
flask run
```
and, visit http://localhost:5000

For production deployment, I used [gunicorn](https://gunicorn.org/). 

Since the site is down now, you can also use `images.py` as a command-line bernie meme creation tool with
```
python images.py 'FILENAME.jpg' 'LOCATION' 
```

If you plan on exceeding the rate limits or call cap, make sure to sign the url with `-s` or `--sign` (this also happens by default). If you're just doing this for fun, or want to look at a request url without the signature, you can use `-n` or `--no-sign`.


`Procfile` and `Aptfile` are required to deploy with [Heroku](https://heroku.com/)

## Licensing
This site is licensed under the [GNU Affero General Public License](https://www.gnu.org/licenses/agpl-3.0.en.html)

