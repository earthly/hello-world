VERSION 0.7

FROM busybox:1.32.0

hello:
    ARG name=world
    COPY globe.txt /globe.txt
    RUN cat /globe.txt
    RUN echo "Hello, $name!" > /hello.txt
    CMD ["cat", "/hello.txt"]
    SAVE ARTIFACT /hello.txt AS LOCAL hello.txt
    SAVE IMAGE hello:latest

hello-slow:
    BUILD +hello
    RUN sleep 3
    RUN echo "Running slow operation. This will take 20 seconds..."
    RUN sleep 20
    RUN echo "...done!"
    RUN echo "Running this target again will skip these steps."
