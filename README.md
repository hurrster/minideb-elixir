minideb-elixir
==============

A bunch of minimalistic Docker base images for Elixir based on [minideb](https://github.com/bitnami/minideb)

```
REPOSITORY          TAG                 IMAGE ID            CREATED             SIZE
hurrster/elixir     1.2.6               a480f5824601        8 minutes ago       128.8 MB
hurrster/elixir     1.3.4               e1f0437ece6c        12 minutes ago      140.8 MB
hurrster/elixir     1.4.0               a524f80d3222        28 minutes ago      141.9 MB
elixir              1.4-slim            e17a97f44ad0        10 days ago         381.8 MB
elixir              1.4                 628a70010c58        10 days ago         826.2 MB
elixir              1.3                 d63929a1892d        4 weeks ago         825.9 MB
```

You can use image directly:

    $ sudo docker run -it hurrster/elixir:latest

Or use it as a base in your Dockerfile:

    FROM hurrster/elixir:1.4
