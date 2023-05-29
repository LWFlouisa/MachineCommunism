## Possible Implementation
But don't implement just yet.

## Source Code Example
~~~ruby
def add_new_feature
  ## Install a new feature in _data/#{dataset_name}/{dataset_name}.nb
  curated_datasets = File.readlines("_data/curated_datasets/datasets.txt")

  print "Which dataset do you want to install? >> "; input = gets.chomp.to_i

  system("git clone #{curated_datasets[input]}")
end

def remove_broken_feature
  ## If there is conflict of dependencies, uninstall dataset from _data/#{dataset_name}/#{dataset_name}.b
  feature_set = File.readlines("_input/ideas/features.txt") # Note that features must be formatted like a _data / feature / feature.nb
  
  print "Which dataset is has a conflict? >> "; input = gets.chomp.to_i

  broken_dataset = featureset[input]

  system("rm -r #{broken_dataset}")
end

interferance = false

feature_set   = File.readlines("_input/ideas/features.txt")
feature_limit = feature_set.size.to_i

row = 0

feature_limit.times do
  if interferance == false
    add_new_feature
  else
    remove_broken_feature
  end

  sleep(1)

  row = row + 1
end
~~~
