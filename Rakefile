task :build do
  sh "docker build . --build-arg hostuid=$(id -u) --build-arg hostgid=$(id -g) --build-arg hostuser=$(whoami) --build-arg hostgroup=$(whoami) --tag pidrone_pkg:ente"
end

task :create do
  sh "docker rm pidrone_pkg || true"
  sh "docker create -i -t --name pidrone_pkg --privileged --volume /home/duckie/catkin_ws:/home/duckie/catkin_ws pidrone_pkg:ente"
end

task :run do
  sh "docker start --attach -i pidrone_pkg"
end
