# README

## Installation

Copy the file `bin/skype` into your executable folder (like `/usr/local/bin` or `$HOME/bin`):

```sh
sudo curl -sLo /usr/local/bin/skype "https://github.com/timonier/skype/raw/master/bin/skype"
sudo chmod +x /usr/local/bin/skype
```

Linux users can use the [installer](https://github.com/timonier/skype/blob/master/bin/installer):

```sh
curl -sL "https://github.com/timonier/skype/raw/master/bin/installer" | sudo sh -s install
```

## Usage

Run the command `skype`:

```sh
skype
# Start skype
```

__Note__: By default, the version `4.3.0.37` will be used. To change the version, define the `TAG` before the command. For example:

```sh
skype -v
# Skype 4.3.0.37
# © 2014 Skype and/or Microsoft

TAG="..." skype -v
# ...
```

## Contributing

1. Fork it.
2. Create your branch: `git checkout -b my-new-feature`.
3. Commit your changes: `git commit -am 'Add some feature'`.
4. Push to the branch: `git push origin my-new-feature`.
5. Submit a pull request.

__Note__: Use the script `bin/build` to test your modifications locally.

## Links

* [image "timonier/skype"](https://hub.docker.com/r/timonier/skype/)
* [skype](http://www.skype.com//)
