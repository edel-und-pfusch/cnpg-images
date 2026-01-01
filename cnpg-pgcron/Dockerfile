FROM ghcr.io/cloudnative-pg/postgresql:18.1-system-trixie

# To install any package we need to be root
USER root

# We update the package list, install our package
RUN set -xe; \
	apt-get update; \
	apt-get install -y --no-install-recommends postgresql-18-cron; \
	rm -fr /tmp/* ; \
	rm -rf /var/lib/apt/lists/*;

# Change to the uid of postgres (26)
USER 26
