# Download Facebook Tagged Photos

Download all photos a user is tagged in on Facebook.

### Installation using your favorite Terminal application on MacOS

#### Install Homebrew if you don't already have it.
```sh
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

#### Use brew to install system dependencies
```sh
brew install pyenv pyenv-virtualenv
pyenv install 3.7.2
pyenv virtualenv 3.7.2 facebook-tagged-photos
pyenv local facebook-tagged-photos
```

*If you're running MacOS Mojave, you may run into problems with the above commands, which could be solved by the commands below which install xcode command line tools and the associated headers package.*

```sh
xcode-select --install
```

```sh
sudo installer -pkg /Library/Developer/CommandLineTools/Packages/macOS_SDK_headers_for_macOS_10.14.pkg -target /
```

#### Install python dependencies

```
pip install -r requirements.txt
```

### Running

Run the below command in the command line from within the project directory - you will be prompted to log in to Facebook so that the script can begin working.

```
python facebook_photos.py
```

If you'd prefer to have the photos saved elsewhere, provide another argument of the desired output directory. This results in the following command.

```
python facebook_photos.py <your_output_directory>
```
