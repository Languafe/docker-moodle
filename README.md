# docker-moodle

Trying to create a repo to make it super simple to spin up a local Moodle.

Moodle has been added as a [submodule](https://git-scm.com/book/en/v2/Git-Tools-Submodules).

> This setup doesn't include development setup for the H5P plugin itself. To work on the plugin with this setup that you can clone `github.com:/h5p/moodle-mod_hvp` directly into `moodle/mod/hvp`. Moodle will automatically detect the presence of the plugin and prompt you to perform the installation/database modifications that are required.

## TL;DR

Clone this repo with the `--recurse-submodules` flag added to automatically initialize and update the moodle submodule.

```
git clone git@github.com:languafe/docker-moodle.git --recurse-submodules
```

If you already cloned the repo without doing this, you must manually initialize and update the submodule:

```
git submodule update --init
```

Ensure `www-data` has write permissions on the `moodle` directory.

```
docker compose exec php bash
chown www-data:www-data -R ./
```

Visit http://localhost:8100 and perform the installation.

## Updating moodle

Go into the moodle directory and checkout the branch containing the new version we want.

```
cd moodle
git branch checkout MOODLE_311_STABLE
```

Then, to commit this updated state of the submodule:

```
cd ..
git add moodle
git commit -m "Checkout Moodle 3.11"
```
