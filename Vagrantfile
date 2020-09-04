Vagrant.configure("2") do |config|
  config.vm.box = "krec/ubuntu2004-x64"
  config.vm.define "windows_host"

  if ARGV[0] == "up"
    print "Set name for your vm which contains ansible for your windows host:\n"
    VM_NAME = STDIN.gets.chomp
  else
    VM_NAME = "not-necessary"
  end
    
  class WinUsername
    def to_s
	    print "IMPORTANT: You user or create a local windows admin account:\n"
      print "Please type in your local windows admin username:\n"
      STDIN.gets.chomp
    end
  end
  
  class WinPassword
    def to_s
	  begin
        system 'stty -echo'
        print "Please type in your local windows admin password:\n"
        pass = URI.escape(STDIN.gets.chomp)
      ensure
        system 'stty echo'
      end
      pass
    end
  end 

  config.vm.provider :virtualbox do |vb|
    vb.name = VM_NAME
  end
  
  config.vm.provision "ansible_local" do |ansible|	
    ansible.playbook = "ansible/playbook.yml"
    ansible.host_vars = {
      "windows_host" => { 
        "ansible_user" => WinUsername.new,
        "ansible_password" => WinPassword.new,
        "ansible_host" => "10.0.2.2" }
    }
  end
end