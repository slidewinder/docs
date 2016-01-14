# Setting up for `slidewinder` development

## developer tools

If you're on OSX, you'll need to install either XCode (free from the App Store) or [the command-line developer tools](http://osxdaily.com/2014/02/12/install-command-line-tools-mac-os-x/).

## installing Node.js

Whatever operating system you use, you'll need to install Node.js. We recommend doing this using **nvm** - the **n**ode **v**ersion **m**anager. Your machine should come with at least one of `curl` or `wget`. You can use either to install `nvm`:

`curl` version:

```bash
curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.30.1/install.sh | bash
```

`wget` version:

```bash
wget -qO- https://raw.githubusercontent.com/creationix/nvm/v0.30.1/install.sh | bash
```

Follow the instructions that appear in the terminal - it will ask you to close once it's done.

After you've closed and re-opened your terminal, you'll need to tell `nvm` to install the latest version of Node, and set it as default:

```bash
nvm install node
nvm use node
nvm alias default node
```

## installing Coffeescript

Just run:

```
npm install --global coffee-script
```

## getting the `slidewinder` code

If you're going to contribute code you should first *fork* the `slidewinder` repository, then clone your fork.

Use the `fork` button at the top-right of the repository to create your own fork.

<img src="/docs/static/img/fork_button.png" style="width: 100%" />

Now clone your fork (replace 'myname' with your username):

```bash
git clone https://github.com/myname/slidewinder.git
cd slidewinder
```

## installing the dependencies

The project is set up to handle all it's own dependencies from this point. You just need to tell it to install them, by running this command in the slidewinder directory:

```bash
npm install
```

## running the tests

The project has a test script already set up with `cake`, the coffeescript build manager.

You run it with:

```bash
cake test
```

You should see some colourful output (all green if all tests are passing).

## now you're ready!

Contratulations! Now you're ready to start developing.
