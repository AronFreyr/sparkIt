# sparkIt
Simple Spark Java app with support for Selenium testing.

## Getting started

### Requirements
* Java JDK (openjdk-7-jdk recommended)

### Clone and run!
1. `git clone` this repo
2. `./gradlew run` in the repo's base folder
3. Check out a random joke on [localhost:4567](http://localhost:4567)
4. Check out a specific joke (number 5) on [localhost:4567/id/5](http://localhost:4567/id/5)

To run SparkApp on another port ID, export PORT environmental variable to a valid integer port and it will be used.

## Running tests

### Unit tests
1. `./gradlew test` - simple enough.

### Functional tests - Selenium

#### Requirements
1. For running locally on your Windows/MacOS/Linux computer, you'll need to install Firefox 28.0
    * Newer versions might work, but 28.0 will work, so ...
    * You can grab [Firefox 28.0 here](https://ftp.mozilla.org/pub/mozilla.org/firefox/releases/28.0/).
    * Friendly note: Make sure autoupdate is turned off.
    * For all systems you must expose Firefox in your path (how to do so depends on what OS you are running, so please Bing for answers).
2. For running on Servers (GreenQloud for example) where you do not have a GUI, you'll need to install X Virtual Frame Buffer (xvfb) and additional packages and Firefox 28.0.
    * `sudo apt-get install -y xvfb`
    * `sudo apt-get install -y xfonts-100dpi xfonts-75dpi xfonts-scalable xfonts-cyrillic`
    * `sudo apt-get install -y firefox=28.0+build2-0ubuntu2`

**Note** if installing firefox on the server doesn't work, you can do the following:

```sh
cd /tmp
wget https://ftp.mozilla.org/pub/mozilla.org/firefox/releases/28.0/linux-x86_64/en-US/firefox-28.0.tar.bz2
tar xvjf firefox-28.0.tar.bz2
sudo mv firefox/ /opt/firefox28
sudo ln -s /opt/firefox28/firefox /usr/bin/firefo
```

#### Run it!
1. Locally just do `./gradlew selenium`
2. Headless mode on servers:
    * `export DISPLAY=:99`
    * `./gradlew seleniumXvfb`

#### And what? ...
Gradle creates test reports for us. Look at the `build/reports` folder for more sweet Gradle juice.
