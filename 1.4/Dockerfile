FROM bitnami/minideb:jessie

RUN install_packages ca-certificates locales make curl
RUN locale-gen C.UTF-8 && update-locale LANG=C.UTF-8
ENV LANG=C.UTF-8 LANGUAGE=C.UTF-8 LC_ALL=C.UTF-8

RUN curl -O https://packages.erlang-solutions.com/erlang-solutions_1.0_all.deb \
	&& dpkg -i erlang-solutions_1.0_all.deb \
	&& rm erlang-solutions_1.0_all.deb

RUN install_packages erlang-base erlang-dev erlang-syntax-tools erlang-parsetools erlang-ssl erlang-inets

RUN curl https://codeload.github.com/elixir-lang/elixir/tar.gz/v1.4.0 -o "elixir-1.4.0.tar.gz" \
	&& tar xzvf elixir-1.4.0.tar.gz \
	&& cd elixir-1.4.0 \
	&& make clean compile install \
	&& cd .. \
	&& rm -rf elixir* \
	&& apt-get purge -y --auto-remove curl make

CMD ["iex"]
