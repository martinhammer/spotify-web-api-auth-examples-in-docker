FROM mhart/alpine-node

MAINTAINER Martin Hammer (https://github.com/martinhammer)

LABEL Description="Spotify Web API Auth Examples inside Docker"

ENV PATH=$PATH:/github/web-api-auth-examples

RUN mkdir -v /github

WORKDIR /github

RUN \
    apk add --no-cache git && \
    git clone https://github.com/spotify/web-api-auth-examples /github/web-api-auth-examples && \
    cd /github/web-api-auth-examples && \
	apk del git && \
	npm install

WORKDIR /github/web-api-auth-examples/authorization_code

# REPLACE BELOW VALUES WITH YOUR OWN
ENV \
	CLIENT_ID='b763e5550e4d494590ed8b57844abb1a' \
	CLIENT_SECRET='77c8003356f34f0d855c8afc1463e7ca' \
	REDIRECT_URI='http://localhost:8888/callback'

RUN \
	sed -i -e s#CLIENT_ID#"$CLIENT_ID"#g app.js && \
	sed -i -e s#CLIENT_SECRET#"$CLIENT_SECRET"#g app.js && \
	sed -i -e s#REDIRECT_URI#"$REDIRECT_URI"#g app.js

EXPOSE 8888

CMD ["node", "app.js"]
