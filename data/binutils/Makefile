all: bin-utils-cve_2017_14745

bin-utils-cve_2017_14745:
	docker build . -t "$@" \
	  --build-arg SUT_VERSION=7a31b38ef87d133d8204cae67a97f1989d25fa18 \
	  --build-arg BUG_DIR=cve_2017_14745

.PHONY: bin-utils-cve_2017_14745
