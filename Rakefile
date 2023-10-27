require 'confidante'

configuration = Confidante.configuration

desc "Lookup greeting"
task :greet, [:environment] do |task, args|
  configuration = configuration.for_scope(args.to_h.merge(role: args[:environment]))
  puts "Hello: " + configuration.name
end
