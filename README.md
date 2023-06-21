# Inline Games [![License](https://img.shields.io/github/license/FanatasticSukhi/inlinegamesbot.svg)](https://github.com/FantasticSukhi/inlinegamesbot/blob/master/LICENSE) [![Telegram](https://img.shields.io/badge/Telegram-%40MAMBAGAME_GBOT-blue.svg)](https://t.me/MAMBAGAMES_GBOT)

A Telegram bot that provides real-time multiplayer games that can be played in any chat.

You can see the bot in action by messaging [@inlinegamesbot](https://t.me/MAMBAGAMES_GBOT).

Currently hosted on [Fly.io](https://fly.io/) platform.

#### Currently available games:

- Tic-Tac-Toe
- Tic-Tac-Four ([@DO97](https://github.com/DO97))
- Elephant XO ([@DO97](https://github.com/DO97))
- Connect Four
- Rock-Paper-Scissors
- Rock-Paper-Scissors-Lizard-Spock ([@DO97](https://github.com/DO97))
- Russian Roulette
- Checkers
- Pool Checkers

## Deploying

### Heroku
<details>
  <summary>Instructions</summary>

Use this button to begin deployment:  
[![Deploy](https://www.herokucdn.com/deploy/button.svg)](https://heroku.com/deploy?template=https://github.com/FantasticSukhi/inlinegamesbot)

Assuming everything was entered correctly your bot should be instantly working - if it's not you should try running `php bin/console post-install` inside the app.

You will also want to add **Heroku Scheduler** addon and set up a hourly task to run the following command to clean up expired games from the database:
- `php bin/console cron`

_If this command times out too fast try using something like this instead: `php -d max_execution_time=2700 bin/console cron`_
</details>

### Google Cloud Platform
<details>
  <summary>Instructions</summary>

- Install dependencies with `composer install`
- Copy `env_variables.example.yaml` into `env_variables.yaml` and fill out the details
- Run the deployment command: `gcloud app deploy --project YOUR-PROJECT-NAME-HERE app.yaml cron.yaml`
- Visit `https://YOUR-PROJECT-NAME-HERE.appspot.com/admin?a=post-install` to perform post-install tasks
</details>

### Fly.io

<details>
  <summary>Instructions</summary>

- `flyctl apps create`
- `flyctl volumes create data --size=1`
- `flyctl secrets set BOT_TOKEN=`
- `flyctl secrets set BOT_USERNAME=`
- `flyctl secrets set BOT_WEBHOOK=YOUR-APP-NAME.fly.dev`
- `flyctl secrets set BOT_SECRET=`
- If you want to use web+worker setup you have to replace `web:` line in `Procfile`
- `flyctl deploy`

</details>

## Note on translations

Translations support is implemented but it is not used mainly because translated text would be displayed to both players - this could be problematic in "gaming" groups - people setting language that other player can't understand!

## Contributing

See [CONTRIBUTING](CONTRIBUTING.md) for more information.

## License

See [LICENSE](LICENSE).
