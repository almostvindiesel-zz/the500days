# ############################################################ INSTALLATION
virtualenv venv
. venv/bin/activate
pip install -r requirements.txt
python app.py


# For Heroku
virtualenv venv
source venv/bin/activate
pip install flask (no sudo needed)
pip install gunicorn
pip freeze > requirements.txt
echo 'psycopg2' >> requirements.txt
echo 'requests' >> requirements.txt
heroku create
git push heroku master -f
heroku ps:scale web=1
heroku open

heroku local web


# ############################################################ 
Visit this link to get the access token:
https://api.instagram.com/oauth/authorize/?client_id=fc522f8ae493478c9b83009bac960755&redirect_uri=http%3A%2F%2Fjoanneandjohn.com%2F500days&response_type=token 


curl \-F 'client_id=CLIENT-ID' \
    -F 'client_secret=CLIENT-SECRET' \
    -F 'grant_type=authorization_code' \
    -F 'redirect_uri=YOUR-REDIRECT-URI' \
    -F 'code=CODE' \
    https://api.instagram.com/oauth/access_token