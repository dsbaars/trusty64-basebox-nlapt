trusty64-veewee-nlapt
=====================

Ubuntu 14.04(.1) LTS Basebox generator (Vagrant)

```sh
├── ubuntu-14.04-dsb-utwente-parallels       # Ubuntu 14.04 for Parallels 9.0 with all provisioners
├── ubuntu-14.04-dsb-utwente-vbox            # Ubuntu 14.04 for Virtualbox with all provisioners
├── ubuntu-14.04.1-beaker-amd64              # Ubuntu 14.04.1 for Parallels 10, optimized for use with Beaker
└── ubuntu-14.04.1-dsb-utwente-parallels     # Ubuntu 14.04.1 for Parallels 10, without provisioners
```

#### Requirements
- vagrant: http://www.vagrantup.com/downloads.html
- veewee: https://github.com/jedi4ever/veewee

##### Parallels Boxes
- Parallels Desktop 9 For Mac: http://www.parallels.com/downloads/desktop/
- Parallels Virtualization SDK: http://download.parallels.com//desktop/v9/update2.hf1/ParallelsVirtualizationSDK-6.0.24229.991745.dmg
- vagrant-parallels plugin: https://github.com/Parallels/vagrant-parallels

##### VirtualBox Boxes
- VirtualBox: https://www.virtualbox.org/wiki/Downloads

#### Installing Veewee with RVM
<sup>(Original: https://github.com/jedi4ever/veewee/blob/master/doc/installation.md)</sup>

Clone the veewee project from source:

    $ cd <path_to_workspace>
    $ git clone https://github.com/jedi4ever/veewee.git
    $ cd veewee

Set the local gemset and ruby version within the current directory:

    $ rvm use 1.9.2@veewee --create

Run `bundle install` to install Gemfile dependencies for our local gemset:

    $ gem install bundler
    $ bundle install

### Build boxes
    $ bundle exec veewee parallels build 'ubuntu-14.04-dsb-utwente-parallels'
    $ bundle exec veewee vbox build 'ubuntu-14.04-dsb-utwente-vbox'

### Export boxes
    $ bundle exec veewee parallels export 'ubuntu-14.04-dsb-utwente-parallels'
    $ bundle exec veewee vbox export 'ubuntu-14.04-dsb-utwente-vbox'

#### Troubleshooting
Did you install Python via Homebrew? Create a symlink:

    $ sudo ln -fs /Library/Frameworks/ParallelsVirtualizationSDK.framework/Libraries/Python/2.7/prlsdkapi /Library/Python/2.7/site-packages/
