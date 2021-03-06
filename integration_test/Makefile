DOCKER_BUILD_OPTS = -t pganalyze-collector-test ..
DOCKER_RUN_CMD = docker run --name pganalyze-collector-test -v `pwd`/docker-entrypoint-initdb.d:/docker-entrypoint-initdb.d/ -d pganalyze-collector-test

.PHONY: pg92 pg93 pg94 pg95 pg96 pg10 pg11

all: pg92 pg93 pg94 pg95 pg96 pg10 pg11

pg92:
	docker build -f Dockerfile.test-pg92 $(DOCKER_BUILD_OPTS)
	$(DOCKER_RUN_CMD)
	sleep 10
	docker exec pganalyze-collector-test pgbench -U postgres -i
	docker exec pganalyze-collector-test pgbench -U postgres
	docker exec pganalyze-collector-test sh -c "DB_USERNAME=postgres PGA_API_KEY=dummy PGA_DISABLE_ACTIVITY=1 pganalyze-collector --dry-run --force-state-update -v" > pg92_1.json
	docker exec pganalyze-collector-test pgbench -U postgres
	docker exec pganalyze-collector-test sh -c "DB_USERNAME=postgres PGA_API_KEY=dummy PGA_DISABLE_ACTIVITY=1 pganalyze-collector --dry-run --force-state-update -v" > pg92_2.json
	docker rm -f pganalyze-collector-test
	docker rmi pganalyze-collector-test
	if [ "`jq '.collectorErrors' pg92_2.json | tr -d ' \n\r\t '`" != "null" ]; then \
		jq '.collectorErrors' pg92_2.json; \
		exit 1; \
	fi
	jq '.queryInformations[].normalizedQuery' pg92_2.json | sort --version-sort -f > pg92.out
	diff -Naur pg92.expected pg92.out && echo 'success'

pg93:
	docker build -f Dockerfile.test-pg93 $(DOCKER_BUILD_OPTS)
	$(DOCKER_RUN_CMD)
	sleep 10
	docker exec pganalyze-collector-test pgbench -U postgres -i
	docker exec pganalyze-collector-test pgbench -U postgres
	docker exec pganalyze-collector-test sh -c "DB_USERNAME=postgres PGA_API_KEY=dummy PGA_DISABLE_ACTIVITY=1 pganalyze-collector --dry-run --force-state-update -v" > pg93_1.json
	docker exec pganalyze-collector-test pgbench -U postgres
	docker exec pganalyze-collector-test sh -c "DB_USERNAME=postgres PGA_API_KEY=dummy PGA_DISABLE_ACTIVITY=1 pganalyze-collector --dry-run --force-state-update -v" > pg93_2.json
	docker rm -f pganalyze-collector-test
	docker rmi pganalyze-collector-test
	if [ "`jq '.collectorErrors' pg93_2.json | tr -d ' \n\r\t '`" != "null" ]; then \
		jq '.collectorErrors' pg93_2.json; \
		exit 1; \
	fi
	jq '.queryInformations[].normalizedQuery' pg93_2.json | sort --version-sort -f > pg93.out
	diff -Naur pg93.expected pg93.out && echo 'success'

pg94:
	docker build -f Dockerfile.test-pg94 $(DOCKER_BUILD_OPTS)
	$(DOCKER_RUN_CMD)
	sleep 10
	docker exec pganalyze-collector-test pgbench -U postgres -i
	docker exec pganalyze-collector-test pgbench -U postgres
	docker exec pganalyze-collector-test sh -c "DB_USERNAME=postgres PGA_API_KEY=dummy PGA_DISABLE_ACTIVITY=1 pganalyze-collector --dry-run --force-state-update -v" > pg94_1.json
	docker exec pganalyze-collector-test pgbench -U postgres
	docker exec pganalyze-collector-test sh -c "DB_USERNAME=postgres PGA_API_KEY=dummy PGA_DISABLE_ACTIVITY=1 pganalyze-collector --dry-run --force-state-update -v" > pg94_2.json
	docker rm -f pganalyze-collector-test
	docker rmi pganalyze-collector-test
	if [ "`jq '.collectorErrors' pg94_2.json | tr -d ' \n\r\t '`" != "null" ]; then \
		jq '.collectorErrors' pg94_2.json; \
		exit 1; \
	fi
	jq '.queryInformations[].normalizedQuery' pg94_2.json | sort --version-sort -f > pg94.out
	diff -Naur pg94.expected pg94.out && echo 'success'

pg95:
	docker build -f Dockerfile.test-pg95 $(DOCKER_BUILD_OPTS)
	$(DOCKER_RUN_CMD)
	sleep 10
	docker exec pganalyze-collector-test pgbench -U postgres -i
	docker exec pganalyze-collector-test pgbench -U postgres
	docker exec pganalyze-collector-test sh -c "DB_USERNAME=postgres PGA_API_KEY=dummy PGA_DISABLE_ACTIVITY=1 pganalyze-collector --dry-run --force-state-update -v" > pg95_1.json
	docker exec pganalyze-collector-test pgbench -U postgres
	docker exec pganalyze-collector-test sh -c "DB_USERNAME=postgres PGA_API_KEY=dummy PGA_DISABLE_ACTIVITY=1 pganalyze-collector --dry-run --force-state-update -v" > pg95_2.json
	docker rm -f pganalyze-collector-test
	docker rmi pganalyze-collector-test
	if [ "`jq '.collectorErrors' pg95_2.json | tr -d ' \n\r\t '`" != "null" ]; then \
		jq '.collectorErrors' pg95_2.json; \
		exit 1; \
	fi
	jq '.queryInformations[].normalizedQuery' pg95_2.json | sort --version-sort -f > pg95.out
	diff -Naur pg95.expected pg95.out && echo 'success'

pg96:
	docker build -f Dockerfile.test-pg96 $(DOCKER_BUILD_OPTS)
	$(DOCKER_RUN_CMD)
	sleep 10
	docker exec pganalyze-collector-test pgbench -U postgres -i
	docker exec pganalyze-collector-test pgbench -U postgres
	docker exec pganalyze-collector-test sh -c "DB_USERNAME=postgres PGA_API_KEY=dummy PGA_DISABLE_ACTIVITY=1 pganalyze-collector --dry-run --force-state-update -v" > pg96_1.json
	docker exec pganalyze-collector-test pgbench -U postgres
	docker exec pganalyze-collector-test sh -c "DB_USERNAME=postgres PGA_API_KEY=dummy PGA_DISABLE_ACTIVITY=1 pganalyze-collector --dry-run --force-state-update -v" > pg96_2.json
	docker rm -f pganalyze-collector-test
	docker rmi pganalyze-collector-test
	if [ "`jq '.collectorErrors' pg96_2.json | tr -d ' \n\r\t '`" != "null" ]; then \
		jq '.collectorErrors' pg96_2.json; \
		exit 1; \
	fi
	jq '.queryInformations[].normalizedQuery' pg96_2.json | sort --version-sort -f > pg96.out
	diff -Naur pg96.expected pg96.out && echo 'success'

pg10:
	docker build -f Dockerfile.test-pg10 $(DOCKER_BUILD_OPTS)
	$(DOCKER_RUN_CMD)
	sleep 10
	docker exec pganalyze-collector-test pgbench -U postgres -i
	docker exec pganalyze-collector-test pgbench -U postgres
	docker exec pganalyze-collector-test sh -c "DB_USERNAME=postgres PGA_API_KEY=dummy PGA_DISABLE_ACTIVITY=1 pganalyze-collector --dry-run --force-state-update -v" > pg10_1.json
	docker exec pganalyze-collector-test pgbench -U postgres
	docker exec pganalyze-collector-test sh -c "DB_USERNAME=postgres PGA_API_KEY=dummy PGA_DISABLE_ACTIVITY=1 pganalyze-collector --dry-run --force-state-update -v" > pg10_2.json
	docker rm -f pganalyze-collector-test
	docker rmi pganalyze-collector-test
	if [ "`jq '.collectorErrors' pg10_2.json | tr -d ' \n\r\t '`" != "null" ]; then \
		jq '.collectorErrors' pg10_2.json; \
		exit 1; \
	fi
	jq '.queryInformations[].normalizedQuery' pg10_2.json | sort --version-sort -f > pg10.out
	diff -Naur pg10.expected pg10.out && echo 'success'

pg11:
	docker build -f Dockerfile.test-pg11 $(DOCKER_BUILD_OPTS)
	$(DOCKER_RUN_CMD)
	sleep 10
	docker exec pganalyze-collector-test pgbench -U postgres -i
	docker exec pganalyze-collector-test pgbench -U postgres
	docker exec pganalyze-collector-test sh -c "DB_USERNAME=postgres PGA_API_KEY=dummy PGA_DISABLE_ACTIVITY=1 pganalyze-collector --dry-run --force-state-update -v" > pg11_1.json
	docker exec pganalyze-collector-test pgbench -U postgres
	docker exec pganalyze-collector-test sh -c "DB_USERNAME=postgres PGA_API_KEY=dummy PGA_DISABLE_ACTIVITY=1 pganalyze-collector --dry-run --force-state-update -v" > pg11_2.json
	docker rm -f pganalyze-collector-test
	docker rmi pganalyze-collector-test
	if [ "`jq '.collectorErrors' pg11_2.json | tr -d ' \n\r\t '`" != "null" ]; then \
		jq '.collectorErrors' pg11_2.json; \
		exit 1; \
	fi
	jq '.queryInformations[].normalizedQuery' pg11_2.json | sort --version-sort -f > pg11.out
	diff -Naur pg11.expected pg11.out && echo 'success'
