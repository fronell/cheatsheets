# Restart the VM and load changes from Vagrantfile
vagrant reload

# Suspend the VM
vagrant suspend

# Create a new Vagrantfile
vagrant init

# Create a new Vagrantfile with a specific box
vagrant init BOX_NAME

#[====BOX MANAGEMENT====]

# List available boxes
vagrant box list

# Package a VirtualBox VM into a box
vagrant package --output BOX_FILE --base VM_NAME

# Add a box
vagrant box add BOX_NAME BOX_FILE

# Package a VirtualBox VM from its directory into a box
cd ~/VirtualBox\ VMs/VM_NAME
vagrant package --output BOX_FILE --base VM_NAME
