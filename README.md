This is really just a Vagrantfile you can copy into your new Ionic project to
get a VM up that can run the Ionic CLI, including `ionic serve`, which can
be browsed from the host machine's browser at the URL specified in the
Vagrantfile (defaults to `app.ionic.test`).

_Note that since this is a Linux VM, it does not support building for or
emulating iOS. This is meant as a convenient way to get started and
building, and then later check out the code inside a macOS VM that has
Xcode and Ionic and such installed, that can to iOS builds._

## Quick start (new app):

```
# Assume you have copied Vagrantfile into an empty directory,
# and edited its hostname variables and IP address as you see fit.
# Or, if not, that you are happy with http://app.ionic.test/ as our
# test URL.
#
# From the directory that Vagrantfile lives in...

# Bring up the VM and login to it
vagrant up
vagrant ssh

# If you want to create this app on the *host* machine's filesystem
# so that it survives destruction of the VM:
cd /vagrant

# Else, you can check it out inside the VM's filesystem and it
# should work with LiveReload file watching:
cd ~

# Create a new app however you like. See https://ionicframework.com/getting-started
# e.g.:
ionic start --v2 myApp tabs

# Run the app
cd myApp
ionic serve
```

Now open the app on the host machine at http://app.ionic.test/ and play with it!

If you created the app in `/vagrant`, it is on the host machine and you will need
to CTRL-C and restart `ionic serve` and then reload the browser to see changes.
If you created the app inside the VM, you will have to edit inside the VM,
but changes should be immediately reloaded in the browser.

## Quick start (existing app):

```
# Copy this Vagrantfile into your project.
cd your_project_directory
cp path/to/this/Vagrantfile .

# Edit the Vagrantfile as desired to change the hostname

# Bring up VM and run the app
vagrant up
vagrant ssh
cd /vagrant
ionic serve
```

Now open the app on the host machine at http://app.ionic.test/ and play with it!

Your app source is mounted into the VM from the host machine, which means LiveReload
won't work and you will need to CTRL-C and restart `ionic serve` and then reload
the browser to see changes.

