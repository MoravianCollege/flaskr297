# Flaskr

The basic blog app built in the [Flask tutorial](https://flask.palletsprojects.com/tutorial/)


## Install

Create a virtualenv and activate it

```
python3 -m venv .venv
source .venv/bin/activate
```

## Install Flaskr

```
pip install -e .
```

## Run

```
export FLASK_APP=flaskr
export FLASK_ENV=development
flask init-db
flask run
```

Open [http://127.0.0.1:5000](http://127.0.0.1:5000) in a browser.


## Test

```
pip install '.[test]'
pytest
```

## Run with coverage report

```
coverage run -m pytest
coverage report
coverage html
```

open `htmlcov/index.html` in a browser


## Run Manually in AWS Linux

Launch an EC2 instance

* t2.micro (free)
* Leave all settings as default until Step 6
* In "Configure Security Group" click "Add Rule" and then select "HTTP" (all other settings for the rule can be default) 

```
sudo su -
yum install git python3 python3-pip
git clone https://github.com/MoravianCollege/flaskr297.git
cd flaskr397
pip3 install .
pip3 install gunicorn
export FLASK_APP=flaskr
flask init-db
gunicorn -b 0.0.0.0:80 "flaskr:create_app()"
```

Open webpage for AWS instance in a browser (make sure it is http:// and not https://)
