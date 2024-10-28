# Installing pwndrop
FROM ubuntu:24.04 AS build

RUN echo "Installing wget" \
    && apt update \
    && apt install -y wget && \

    echo "Installing pwndrop" \
    && wget https://github.com/kgretzky/pwndrop/releases/latest/download/pwndrop-linux-amd64.tar.gz \
    && tar zxvf pwndrop-linux-amd64.tar.gz

# Ready to work stage
FROM ubuntu:24.04

COPY --from=build /pwndrop /usr/local/pwndrop

EXPOSE 80 443

ENTRYPOINT ["/usr/local/pwndrop/pwndrop"]
