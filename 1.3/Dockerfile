FROM bitnami/minideb:jessie

RUN install_packages ca-certificates curl make
ENV DEBIAN_FRONTEND noninteractive
RUN apt-get update -qq && apt-get install -y locales -qq && locale-gen en_US.UTF-8 en_us && dpkg-reconfigure locales && dpkg-reconfigure locales && locale-gen C.UTF-8 && /usr/sbin/update-locale LANG=C.UTF-8
ENV LANG C.UTF-8
ENV LANGUAGE C.UTF-8
ENV LC_ALL C.UTF-8

RUN curl -O https://packages.erlang-solutions.com/erlang-solutions_1.0_all.deb
RUN dpkg -i erlang-solutions_1.0_all.deb
RUN rm erlang-solutions_1.0_all.deb

RUN apt-get update
RUN install_packages erlang-base erlang-dev erlang-syntax-tools erlang-parsetools erlang-ssl erlang-inets

RUN curl https://codeload.github.com/elixir-lang/elixir/tar.gz/v1.3.4 -o "elixir-1.3.4.tar.gz"
RUN tar xzvf elixir-1.3.4.tar.gz
RUN cd elixir-1.3.4 && make clean compile install
RUN cd .. && rm -rf elixir*

CMD ["iex"]