## Instructions

Create a virtual env, since some of the packages don't yet work with python 3. I got all of the details from here: https://github.com/BurntSushi/nfldb/wiki/Updating-nfldb-with-real-time-data

```
# Create a virtual environment
virtualenv -p /usr/bin/python2.7 nfl

# Activate virtual
source activate ./nfl

# Install the latest version of pip or psycopg2 install will fail
pip install -U pip

# Install the required library
pip install -r requirements.txt

# Update the database
nfldb-update

# Log into postgres and run the following to fix an error:
# DETAIL:  Key (pos_team)=(JAX) is not present in table "team".
INSERT INTO team values('JAX','Jacksonville', 'Jaguars');

```