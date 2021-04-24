

```mac:terminal
docker-compose build api 

 => CACHED [5/9] WORKDIR /app                                                                                                     0.0s
 => CACHED [6/9] COPY package*.json ./                                                                                            0.0s
 => ERROR [7/9] RUN yarn install                                                                                                  1.0s
------                                                                                                                                 
 > [7/9] RUN yarn install:
#12 1.027 /bin/sh: yarn: not found
------
executor failed running [/bin/sh -c yarn install]: exit code: 127
ERROR: Service 'api' failed to build
```

yarn installするけどbin/sh配下にyarnが見つかりませんと。


原因そもそものDockerfileが間違ってapiようではなく
front用であったため

```docker:api>Dockerfile
FROM ruby:2.7.1-alpine

ARG WORKDIR

ENV RUNTIME_PACKAGES="linux-headers libxml2-dev make gcc libc-dev nodejs tzdata postgresql-dev postgresql git" \
    DEV_PACKAGES="build-base curl-dev" \
    HOME=/${WORKDIR} \
    LANG=C.UTF-8 \
    TZ=Asia/Tokyo

# ENV test（このRUN命令は確認のためなので無くても良い）
RUN echo ${HOME}

WORKDIR ${HOME}

COPY Gemfile* ./

RUN apk update && \
    apk upgrade && \
    apk add --no-cache ${RUNTIME_PACKAGES} && \
    apk add --virtual build-dependencies --no-cache ${DEV_PACKAGES} && \
    bundle install -j4 && \
    apk del build-dependencies

COPY . .

CMD ["rails", "server", "-b", "0.0.0.0"]
```

以上
