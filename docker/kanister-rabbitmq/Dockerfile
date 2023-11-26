ARG TOOLS_IMAGE
# FROM registry.access.redhat.com/ubi9/ubi:9.1.0-1646.1669627755 as builder
FROM registry.access.redhat.com/ubi9/ubi:9.1.0-1646.1669627755

RUN dnf upgrade -y && dnf clean all && rm -rf /var/cache/dnf

# # Download the RPM file to avoid timeouts during install
# RUN curl -LO https://dev.mysql.com/get/mysql80-community-release-el9-1.noarch.rpm
# # Install from the local file
# RUN dnf install -y mysql80-community-release-el9-1.noarch.rpm

# RUN dnf install -y mysql-community-client

COPY rabbitmq.repo /etc/yum.repos.d/rabbitmq.repo
RUN dnf update -y && dnf install -y rabbitmq-server perl-Digest-SHA

RUN curl https://raw.githubusercontent.com/kanisterio/kanister/master/scripts/get.sh | bash
CMD [ "/usr/bin/tail", "-f", "/dev/null" ]

# FROM $TOOLS_IMAGE

# RUN microdnf -y update && microdnf -y install tar gzip && \
#     microdnf clean all

# COPY --from=builder /usr/sbin/rabbitmqctl /usr/bin/
# COPY --from=builder /usr/bin/mysql* /usr/bin/
