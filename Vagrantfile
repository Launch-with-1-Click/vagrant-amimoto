# encoding: utf-8
# vim: ft=ruby expandtab shiftwidth=2 tabstop=2

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "dummy"
  config.vm.box_url = "https://github.com/mitchellh/vagrant-aws/raw/master/dummy.box"


  ## AWS
  config.vm.provider :aws do |aws, override|
    aws.access_key_id     = ENV['AWS_ACCESS_KEY']
    aws.secret_access_key = ENV['AWS_SECRET_ACCESS_KEY']
    aws.keypair_name      = ENV['AWS_EC2_KEYPAIR']

    aws.region = "ap-northeast-1"
    aws.ami = "ami-9160da90"

    aws.security_groups = 'default'
    aws.instance_type = "m1.medium"

    override.ssh.username = "ec2-user"
    override.ssh.private_key_path = ENV['AWS_EC2_KEYPAIR_PATH']
  end

end
