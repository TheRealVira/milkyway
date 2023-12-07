FROM node:lts-alpine
RUN apk update && apk add curl wget rsync tar
RUN mkdir /data
WORKDIR /data
RUN curl -s https://api.github.com/repos/Pf2eToolsOrg/Pf2eTools/tags | grep tarball_url | grep v. | cut -d '"' -f 4 | head -n 1 | wget -O Pf2eTools.tar.gz -qi - && tar xzf Pf2eTools.tar.gz --strip-components=1 && rm Pf2eTools.tar.gz
RUN sed -i '/this is a mirror, and is not guaranteed to be up-to-date/d' index.html
RUN npm install && npm install -g http-server && npm run build:sw:prod
COPY . .
VOLUME /data/homebrew
EXPOSE 8080
CMD [ "http-server", "-b", "-g", "--cors", "-s", "-p", "8080" ]