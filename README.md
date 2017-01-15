# Vagrant Files

Collection of personal vagrant files.

## Customisation

Most Vagrantfiles include:

```ruby
client_vagrantfile = File.expand_path('../Vagrantfile.client', __FILE__)
load client_vagrantfile if File.exist?(client_vagrantfile)
```

Therefore, if you'd like to have custom configuration that you'd like to non put
under source control, you can create and ignore the `Vagrantfile.client` file.

The contents might look something like this:
```ruby
# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.vm.synced_folder "/some/host/path", "/some/guest/path"

  config.vm.provider "virtualbox" do |vb|
    vb.memory = "768"
  end
end
```

> **Note:** The `Vagrant` block must be present in the `Vagrantfile.client`.
