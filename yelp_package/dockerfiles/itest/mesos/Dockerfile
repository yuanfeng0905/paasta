# Copyright 2015-2016 Yelp Inc.
#
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
#
#     http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.

FROM ubuntu:trusty
RUN echo "deb http://repos.mesosphere.com/ubuntu trusty main" > /etc/apt/sources.list.d/mesosphere.list
RUN echo "deb http://apt.dockerproject.org/repo ubuntu-trusty main" > /etc/apt/sources.list.d/docker.list
RUN apt-key adv --keyserver keyserver.ubuntu.com --recv 58118E89F3A912897C070ADBF76221572C52609D
RUN apt-key adv --keyserver keyserver.ubuntu.com --recv 81026D0004C44CF7EF55ADF8DF7D54CBE56151BF
RUN apt-get update && apt-get -y install libsasl2-modules mesos=1.1.0-2.0.107.ubuntu1404

RUN apt-get -y install docker-engine=1.10.3-0~trusty
ADD mesos-secrets /etc/mesos-secrets
ADD mesos-slave-secret /etc/mesos-slave-secret
RUN echo '{}' > /root/.dockercfg
RUN chmod 600 /etc/mesos-secrets
