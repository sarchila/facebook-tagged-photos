# Download Facebook Tagged Photos

Download all photos a user is tagged in on Facebook.

## Installation using your favorite Terminal application on MacOS

### Install Homebrew if you don't already have it.
```sh
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

### Use brew to install system dependencies


#### 1. Run the following in your terminal only if you have not previously installed pyenv and pyenv-virtualenv before.
These commands only need to be run once, so if you have already installed pyenv and pyenv-virtualenv and have them working on your machine, skip down to step 3.
```sh
brew install pyenv pyenv-virtualenv
echo -e '\n# pyenv init\nif command -v pyenv 1>/dev/null 2>&1; then\n  eval "$(pyenv init -)"\nfi' >> ~/.bash_profile
echo -e '\n# pyenv-virtualenv init\nif which pyenv-virtualenv-init > /dev/null; then\n  eval "$(pyenv virtualenv-init -)"\nfi' >> ~/.bash_profile
```


#### 2. Run the following to trigger the pyenv and pyenv-virtualenv init commands that you've just added to your bash_profile.
```sh
source ~/.bash_profile
```


#### 3. With pyenv and pyenv-virtualenv installed and initialized on your machine, you can now use them to manage your python versioning.
```sh
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

#### 4. Install python dependencies

```
pip install -r requirements.txt
```

## Running

- Run the below command in the command line from within the project directory - you will be prompted to log in to Facebook so that the script can begin working.
```sh
python facebook_photos.py
```

OR

- If you'd prefer to have the photos saved elsewhere, provide another argument of the desired output directory. e.g. if you'd like to save your photos in a `facebook_photos` folder under Downloads, you can run the following command to create the output directory and run the script to store your downloaded photos there
```sh
mkdir ~/Downloads/facebook_photos && python facebook_photos.py ~/Downloads/facebook_photos
```
