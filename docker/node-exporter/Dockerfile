FROM quay.io/prometheus/node-exporter

RUN mkdir -p /var/lib/prometheus/node-exporter

COPY docker-entrypoint.sh /usr/local/bin/docker-entrypoint
RUN chmod +x /usr/local/bin/docker-entrypoint

ENV ENV /root/.shinit
COPY env.sh /root/
RUN \
	{ \
		echo '. ~/env.sh'; \
	} >> /root/.shinit

ENTRYPOINT ["docker-entrypoint"]
CMD ["node_exporter"]
