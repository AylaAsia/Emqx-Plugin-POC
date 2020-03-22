FROM erlang:22.1-alpine
# RUN sed -i 's/dl-cdn.alpinelinux.org/mirrors.ustc.edu.cn/g' /etc/apk/repositories
RUN apk add git \
        curl \
        gcc \
        g++ \
        make \
        perl \
        ncurses-dev \
        openssl-dev \
        coreutils \
        bsd-compat-headers \
        libc-dev \
        libstdc++
RUN git clone -b v4.0.5 --depth 1 https://github.com/emqx/emqx-rel.git /emqx-rel
COPY rebar.config /emqx-rel/
RUN cd /emqx-rel \
        && make
CMD /emqx-rel/_build/emqx/rel/emqx/bin/emqx foreground
ENTRYPOINT /emqx-rel/_build/emqx/rel/emqx/bin/emqx foreground
