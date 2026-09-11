FROM homebridge/homebridge:2026-09-02

# Add jq for safe JSON edits
RUN \
apt-get -y -qq update && \
apt-get -y -qq install --no-install-recommends ca-certificates jq && \
rm -rf /var/lib/apt/lists/*

# Keep npm cache off disk (good for SD cards)
ENV NPM_CONFIG_CACHE=/tmp/npm-cache

COPY init-with-z2m.sh /usr/local/bin/init-with-z2m.sh
RUN chmod +x /usr/local/bin/init-with-z2m.sh

ENTRYPOINT ["/usr/local/bin/init-with-z2m.sh"]
