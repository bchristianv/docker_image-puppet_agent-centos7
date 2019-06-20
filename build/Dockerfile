FROM centos:7

ARG version="6.5.0-1"

ENV PUPPET_AGENT_VERSION="$version"

RUN yum -y update && \
    yum -y install ca-certificates https://yum.puppet.com/puppet6/el/7/x86_64/puppet-agent-"$PUPPET_AGENT_VERSION".el7.x86_64.rpm && \
    yum clean all && \
    rm -rf /var/cache/yum

ENV PATH=/opt/puppetlabs/server/bin:/opt/puppetlabs/puppet/bin:/opt/puppetlabs/bin:$PATH

ENTRYPOINT ["/opt/puppetlabs/bin/puppet"]
CMD ["agent", "--verbose", "--onetime", "--no-daemonize", "--summarize" ]

COPY Dockerfile /
