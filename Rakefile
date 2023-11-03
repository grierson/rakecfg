require 'confidante'

configuration = Confidante.configuration

desc "Lookup database"
task :database, [:deployment] do |task, args|
  scope = ({:deployment => args[:deployment]})
  configuration = configuration.for_scope(scope)
  puts "DB Host: " + configuration.database_host
end
