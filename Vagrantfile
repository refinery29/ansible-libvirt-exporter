Vagrant.configure(2) do |config|
  config.vm.box = 'ubuntu/xenial64'
  config.vm.provision :shell,
    inline: 'sudo apt-get install -y python-minimal'
  config.vm.provision :ansible,
    playbook: 'playbooks/libvirt-exporter.yml',
    groups: { 'libvirt-exporter' => %w(default)},
    raw_arguments: %w(-vv --diff --become)
end
