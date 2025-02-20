# k6 Documentation
![Staging](https://github.com/k6io/docs/workflows/Staging/badge.svg)
![Production](https://github.com/k6io/docs/workflows/Production/badge.svg)

This repo contains the source code of the [k6 documentation](https://k6.io/docs/).

## Contributing

For small changes and spelling fixes, we recommend using the GitHub UI because the markdown files are relatively easy to edit.

For larger contributions, consider running the project locally to see how the changes look like before making a pull request. 

Markdown files for the documentation are located in [`src/data/markdown/docs`](src/data/markdown/docs) folder. The URL structure is generated based on the folder structure and file names.

The markdown files support a few custom extensions explained on the [File Format Guide](CONTRIBUTING_FILE_FORMAT.md). 

## Install and run in Docker

This uses `docker-compose` and port `8100`.

```shell
git clone git@github.com:k6io/docs.git
cd docs
cp .env.example .env.development

docker-compose  up -d --build
```

Note that starting up the Docker takes several minutes, during which the
website will not be accessible. Use `docker-compose logs -f web` to track
progress.

Then visit http://localhost:8100

> If you want to re-run the `--build` command, you may get an error about not having access to delete a `cache/` folder. Use `sudo` to delete this manually before retrying.


## Manual Installation
If you prefer not to use Docker, you can install the project locally. 
Node 12.x is required.

```bash
git clone git@github.com:k6io/docs.git
cd docs
# nvm use 12.0.0
npm install  # or yarn install
```

Running manually:

```bash
npm start  # or yarn start
```

Visit http://localhost:8000

## Deployment

### To staging
All pull requests merged to `master` will result in an automatic deployment to the staging environment.

### To production
All tags created using the format `vN.N.N`, for instance, `v0.0.1`, will result in an automatic deployment to the production environment. Tags can either be created and pushed from the git cli, or from https://github.com/k6io/docs/releases
