require 'yaml'

namespace :compose do
  desc "build docker compose file"
  task :build do |task|
    docker_compose_hash = {
      "www" => {
        "image" => ENV['IMAGE'],
        "ports" => [
          "80" + ENV['PORTS'] + ":3000"
        ]
      }
    }

    puts docker_compose_hash.to_yaml

    puts "write out docker-compose.yaml"
    File.open('docker-compose.yaml', 'w') {|f| f.write docker_compose_hash.to_yaml }
  end
end
