# docker-moodle

Trying to create a repo to make it super simple to spin up a local Moodle.

Moodle has been added as a [submodule](https://git-scm.com/book/en/v2/Git-Tools-Submodules).

## TL;DR

Clone this repo with the `--recurse-submodules` flag added to automatically initialize and update the moodle submodule.

```
git clone git@github.com:languafe/docker-moodle.git --recurse-submodules
```

If you already cloned the repo without doing this, you must manually initialize and update the submodule:

```
git submodule update --init
```

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
