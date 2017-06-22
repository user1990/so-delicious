![restaurant](https://user-images.githubusercontent.com/13827656/27386429-7c5be802-569e-11e7-841e-782305cc3520.jpg)

# So Delicious
A full stack restaurant application which users can search, geolocate, review and curate their favourite restaurants from around the world.

The application has three main models — Users, Stores and Reviews — all of which are relational. It is designed to hit upon many of today’s application needs such as user authentication, database storage, Ajax REST API, file upload and image resizing.

## Features

- Node.js
- Express
- MongoDB
- Passport JS
- Async/await
- Password Reset
- Sending Email
- AJAX Search

## To Start

To enable ES7 & ES8 features install latest Node.jS >= 8.1.2 version

Install dependencies: ```npm install```

Run app: ```npm start```

### Database

Sign Up to mLab and create new database with the user

Copy your MongoDB URI to variables.env configuration file located in root.

Change ```dbuser``` and ```dbpassword``` with yours from mLab.

Download MongoDB Compass - For interact/analize your data collections with full CRUD functionality.
### Send Email

For sending email with Nodejs use Mailtrap.io — Fake smtp testing server.

Go [here](https://mailtrap.io/) and Sign Up.

In variables.env put your MAIL_USER & MAIL_PASS from mailtrap.io account.
### Google Maps

Get API key from [here](https://developers.google.com/maps/documentation/javascript/get-api-key).

Put the key in MAP_KEY const in variables.env file.

Or use existing one if it's not expired yet.

### Sample Data

```bash
npm run sample
```

If you have previously loaded in this data, you can wipe your database 100% clean with:

```bash
npm run blowitallaway
```

## FAQ

### The Google Maps API key isn't working

The project might have hit a limit with the API key — if this is the case you need to sign up for your own API key over at <https://developers.google.com/maps/documentation/javascript/usage>. You will need to enable static maps for your API key.

Once you have the API key, simply place it in your `variables.env` file and restart.

### I'm getting errors related to `/data/db` like `code:100` and `connection failed`

Check out [this answer](https://stackoverflow.com/questions/7948789/mongodb-mongod-complains-that-there-is-no-data-db-folder#answer-7948986) on stack overflow to get mongoDB running locally.

## I'm getting a `URIError: URI malformed` error when running `npm start`

Thanks to [Chris Ellinger](https://twitter.com/devoidofgenius) for this:

> If you’re getting a `URIError: URI malformed` error when running `npm start`, break out your environment variables. Go into `variables.env` and split the URI like this `MONGO_URI=mongodb://host.com:port` `DB_USER=username` and `DB_PASS=password`. Then inside your `start.js` replace `mongoose.connect(process.env.DATABASE)` with `mongoose.connect(process.env.MONGO_URI, {user: process.env.DB_USER, pass: process.env.DB_PASS});`. I had issues connecting to my mongodb because my password contained symbols.
