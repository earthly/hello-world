VERSION 0.7

FROM busybox:1.32.0

hello:
    COPY globe.txt ./
    RUN cat globe.txt

hello-name:
    ARG name=world
    RUN echo "Hello, $name!"

hello-outputs:
    ARG name=world
    RUN echo "Hello, $name!" > /hello-outputs.txt
    CMD ["cat", "/hello-outputs.txt"]
    SAVE ARTIFACT /hello-outputs.txt AS LOCAL hello-outputs.txt
    SAVE IMAGE hello-outputs:latest
