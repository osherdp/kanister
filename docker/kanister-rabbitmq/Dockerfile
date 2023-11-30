ARG TOOLS_IMAGE
FROM $TOOLS_IMAGE

RUN microdnf install -y python3 \
    && alternatives --install /usr/bin/python python /usr/bin/python3 0
RUN curl https://raw.githubusercontent.com/rabbitmq/rabbitmq-management/v3.7.8/bin/rabbitmqadmin -o /usr/bin/rabbitmqadmin \
    && chmod u+x /usr/bin/rabbitmqadmin
