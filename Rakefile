require 'rake_terraform'
require 'confidante'

configuration = Confidante.configuration
RakeTerraform.define_installation_tasks(
    path: File.join(Dir.pwd, 'vendor', 'terraform'),
    version: '1.6.3')

desc "Lookup database"
task :database, [:deployment] do |task, args|
  scope = ({:deployment => args[:deployment]})
  configuration = configuration.for_scope(scope)
  puts "DB Host: " + configuration.database_host
end

desc "Setup database with Terraform"
namespace :database do
 RakeTerraform.define_command_tasks(
      configuration_name: 'database variables'
  ) do |task, args|
    task.vars = configuration.vars
    task.source_directory = 'infra/database'
    task.work_directory = 'build'
  end
end
