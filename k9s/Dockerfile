FROM derailed/k9s:latest

RUN apk add --update ca-certificates \
    && apk add --update -t deps curl \
    && curl https://amazon-eks.s3.us-west-2.amazonaws.com/1.16.8/2020-04-16/bin/linux/amd64/aws-iam-authenticator -o /usr/local/bin/aws-iam-authenticator \
    && chmod +x /usr/local/bin/aws-iam-authenticator \
    && apk del --purge deps \
    && rm /var/cache/apk/*

RUN mkdir -p /root/.k9s

COPY skins/* /root/.k9s/

RUN  export TERM=xterm-256color

ENTRYPOINT [ "/bin/k9s" ]
