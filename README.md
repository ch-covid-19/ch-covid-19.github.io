# COVID Self report public website

## Local development environment

The frontend uses vue-cli. Please refer to the [official documentation](https://cli.vuejs.org/) for setup instructions.

### Setup

Please be sure to use 'yarn' instead of 'npm' as package manager.

  1. Clone this repository
  2. Create a `.env` file based on the `.env.example` file and fill it with your configuration. See below to learn more about the configuration.
  4. Run `yarn serve` to test locally and `yarn build` to build application

## Translations

Translations are done with the online [POEditor](https://poeditor.com/projects/view?id=327349) service.

The process for translators is the following :

- New keys are added in the frontend by the developers
- New keys are imported in POEditor (done automatically, but with manual trigger, responsibility to be defined)
- Translators are informed of the new keys by notifications
- Translators translates the new keys in POEditor
- Translations are exported in the frontend (done automatically, but with manual trigger, responsibility to be defined)
- The next release includes the new translations

## Contribute

Contributions are welcome through merge requests.

This section will be updated soon...
