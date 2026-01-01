ARG POSTGRES_MAJOR=18

FROM ghcr.io/cloudnative-pg/postgresql:${POSTGRES_MAJOR}.1-system-trixie

# To install any package we need to be root
USER root

# We update the package list, install our package
RUN set -xe; \
	apt-get update; \
	apt-get install -y --no-install-recommends \
		"postgresql-${POSTGRES_MAJOR}-cron" ; \
	rm -fr /tmp/* ; \
	rm -rf /var/lib/apt/lists/*;

# Change to the uid of postgres (26)
USER 26
