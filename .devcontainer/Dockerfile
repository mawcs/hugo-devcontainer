FROM golang:1.13

# Switching to "hugo" will use the standard Hugo version, but will break the integration with Dart Sass.
ARG VARIANT=hugo_extended
# Hugo version to use. Use "latest" for the latest version.
ARG VERSION=latest

RUN apt-get update && apt-get install -y ca-certificates openssl git curl && \
    rm -rf /var/lib/apt/lists/* && \
    case ${VERSION} in \
    latest) \
    export VERSION=$(curl -s https://api.github.com/repos/gohugoio/hugo/releases/latest | grep "tag_name" | awk '{print substr($2, 3, length($2)-4)}') ;;\
    esac && \
    echo ${VERSION} && \
    wget -O ${VERSION}.tar.gz https://github.com/gohugoio/hugo/releases/download/v${VERSION}/${VARIANT}_${VERSION}_Linux-64bit.tar.gz && \
    tar xf ${VERSION}.tar.gz && \
    mv hugo* /usr/bin/hugo && \
    go get github.com/yaegashi/muslstack && \
    muslstack -s 0x800000 /usr/bin/hugo

FROM mcr.microsoft.com/vscode/devcontainers/base
COPY --from=0 /usr/bin/hugo /usr/bin
EXPOSE 1313