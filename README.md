POC For EMQX Plugin in Erlang
====================

This is a POC work to demonstrate how to create a plugin for [EMQX](https://www.emqx.io).

Usage
----------------------

You need `git` and `docker` installed before you play around with it.
After that just build and start it with docker:
```sh
git clone https://github.com/AylaAsia/Emqx-Plugin-POC.git
cd Emqx-Plugin-POC/deploy
docker build -t emqx-plugin-demo .
docker run -d --name emqx --rm -p 18083:18083 -p 1883:1883 emqx-plugin-demo:latest
```
After the container started, login to the EMQX [Dashboard](http://127.0.0.1:18083) through `http://127.0.0.1:18083`

How it works?
-----------------

[Plugin Design](https://docs.emqx.io/broker/v3/en/design.html#plugin-design)

[Hooks Design](https://docs.emqx.io/broker/v3/en/design.html#hooks-design)

Follow-Up works
-----------------

* Optimize the `Dockerfile` stuff to simplify clustering if needed.
* Probably add some real world auth feature in the hooks.

