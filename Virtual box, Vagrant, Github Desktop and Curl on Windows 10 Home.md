#Virtual box, Vagrant, Github Desktop and Curl on Windows 10 Home  
  
##Used software:
  
Windows 10 Home 64-bit  
VirtualBox-5.1.10-112026-Win.exe  
vagrant_1.9.1.msi  
GitHubSetup.exe  
vc_redist.x64.exe  
curl-7.46.0-win64.exe  
  
##Virtual box
  
On Windows 10 Professional / Enterprise Hyper-V must be disabled. Windows Home doesn't come with this option.  
Run the installer from the Explorer via the context-menu / right click menu option with the option "Run as Administrator"  
  
Start Oracle_VM_VirtualBox_Extension_Pack-5.1.10-112026.vbox-extpack. An instance of Virtual Box is executed.  
If errors occur like "the target directory can not be copied", then temporarily disable the filesystem guard of your virusscanner.  
  
Cntl+G shows you the preferences. Choose a default directory with enough space for a few VMs.  

##Vagrant
  
Run vagrant installer downloaded from [the Vagrant site](https://www.vagrantup.com/downloads.html).  
  
#GitHub desktop.  
GitHub Desptop enables you to use Git commands in a cli like powershell or preferably bash.  
  
Get the software from [desktop.github.com](https://desktop.github.com/)  
After login with your git-credentials You'll see an interface with a preferences cogwheel. Choose here:  
 - the default location of your repositories.  
 - the default shell. Git Bash has the best auto-completes.  
   
###Common Errors
####rsync
When you get the following error after "Vagrant up":  
```
"rsync" could not be found on your PATH. Make sure that rsync is properly installed on your system and available on the PATH.
```
Solve this with the next line in your vagrantfile:
```
config.vm.synced_folder ".", "/vagrant", type: "virtualbox"  
```
####"vboxsf" is not available 
After vagrant up you see the following:
```
    default: No guest additions were detected on the base box for this VM! Guest
    default: additions are required for forwarded ports, shared folders, host on                                                                                                                ly
    default: networking, and more. If SSH fails on this machine, please install
    default: the guest additions and repackage the box to continue.
    default:
    default: This is not an error message; everything may continue to work prope                                                                                                                rly,
    default: in which case you may ignore this message.
==> default: Mounting shared folders...
    default: /vagrant => F:/Vagrant/Vagrant_nginx
Vagrant was unable to mount VirtualBox shared folders. This is usually
because the filesystem "vboxsf" is not available. This filesystem is
made available via the VirtualBox Guest Additions and kernel module.
Please verify that these guest additions are properly installed in the
guest. This is not a bug in Vagrant and is usually caused by a faulty
Vagrant box. For context, the command attempted was:

mount -t vboxsf -o uid=1000,gid=1000 vagrant /vagrant

The error output from the command was:

mount: unknown filesystem type 'vboxsf'
```
This is indeed not a problem.  
  
#Curl  
Download and run the [Microsoft Visual C++ 2015 Redistributable.](https://www.microsoft.com/en-us/download/details.aspx?id=48145)  
Download and run [Curl](http://www.confusedbycode.com/curl/#downloads), the admin version.  
RTFM: (https://curl.haxx.se/docs/manual.html)   
   
Enjoy curl!
