# Do not run in client node on your desktop because it will register it as a node!

# Check if chef-shell is in solo mode
puts Chef::Config[:solo].to_s

# Chef Shell will not operate in client/server mode if there is an error in a
# cookbook.  The best way around this is to either use another node that is
# working or pass it a json file that has an empty run list

# Disable echo
echo off

# Assign a node object
stage01 = nodes.show('stage01-01')

# Get all attributes of a node
node.attributes


# Chef Solo notes
node.run_list
node.attributes
node.environment

# Include all recipes including a custom one
node.run_list.expand(node.chef_environment).recipes.each do |r|
  include_recipe r
end

# Enter recipe mode
recipe_mode

# Attributes mode
attributes_mode

# Set the env in the chef run
node.chef_environment("vagrant")

# Save it
node.save
