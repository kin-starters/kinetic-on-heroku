# kinetic-on-heroku

Basic example of a [Kinetic](https://github.com/kin-labs/kinetic) setup on Heroku. It includes:

- Kinetic API with the Kinetic Manager
- A Postgres database
- A Redis instance
- A configured app (`App 1`, with index `1`) on Solana Devnet

After deployment, you can access the Kinetic Manager at `https://<your-app-name>.herokuapp.com` and log in.

Configure the credentials using the `AUTH_USERS` environment variable, or use the default `admin` / `Kinetic1`.

## Requirements

- An account on [Heroku](https://heroku.com)
- The [Heroku CLI](https://devcenter.heroku.com/articles/heroku-cli) if you want to do the manual deploy.

## Usage

### One-click deploy

Fire up a Kinetic instance on [Heroku](https://www.heroku.com/) with a single click:

[![Deploy to Heroku](https://www.herokucdn.com/deploy/button.svg)](https://heroku.com/deploy)

Make sure to update the `API_URL` environment variable to match your Heroku app name. If your app is called `my-kinetic-api`, the `API_URL` should be `https://my-kinetic-api.herokuapp.com/api`.

### Manual deploy

1. Clone this repository and `cd` into it
2. Update the API URL in `app.json` to match your Heroku app name. If your app is called `my-kinetic-api`, the `API_URL` should be `https://my-kinetic-api.herokuapp.com/api`.
3. Login to Heroku with `heroku container:login`
4. Create a new Heroku app: `heroku create -a my-kinetic-api`
5. Push the Docker image to Heroku: `heroku container:push web`
6. Release the image: `heroku container:release web`
7. Open the app: `heroku open`
8. You should see the Kinetic Manager running

# Support

Please head over to the [Kin Developer Community on Discord](https://kin.org/developerdiscord) to get help using Kinetic.
