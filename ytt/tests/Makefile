include $(shell git rev-parse --show-toplevel)/.bootstrap.mk

## Tests

all:: \
  test-celery \
  test-fluentd \
  test-helpers \
  test-namespace-admin \
  test-postgresql \
  test-rabbitmq \
  test-redis \
  test-secrets \
  test-simple-web-app

test-celery::          ## Test celery          YTT library
test-fluentd::         ## Test fluentd         YTT library
test-helpers::         ## Test helpers         YTT library
test-namespace-admin:: ## Test namespace-admin YTT library
test-postgresql::      ## Test postgresql      YTT library
test-rabbitmq::        ## Test rabbitmq        YTT library
test-redis::           ## Test redis           YTT library
test-secrets::         ## Test secrets         YTT library
test-simple-web-app::  ## Test simple-web-app  YTT library
test-%::               ## Test any             YTT library
	printf "\033[0;33mRendering $*: \033[0m"
	error=$$(ytt -f ../lib/$* -f $* 2>&1 > /dev/null) \
	&& echo -e "\033[0;32mOK\033[0m" || (echo -e "\033[0;31mFAIL\033[0m"; echo -e "$$error")
