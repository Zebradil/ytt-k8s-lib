FROM fluent/fluentd:v1.11.5-debian-1.0

USER root

RUN buildDeps="gcc make" \
 && apt-get update \
 && apt-get install -y --no-install-recommends $buildDeps \
 && gem install fluent-plugin-s3 -v "1.4.0" \
 && gem install fluent-plugin-gcs -v "0.4.1" \
 && gem install fluent-plugin-prometheus -v "1.8.5" \
 && gem sources --clear-all \
 && apt-get purge -y --auto-remove $buildDeps \
 && rm -rf /tmp/* /var/tmp/* /usr/lib/ruby/gems/*/cache/*.gem

COPY fluent.conf /fluentd/etc/

USER fluent
