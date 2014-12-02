SHELL:=/bin/mksh

all: syntaxcheck

DIRS:=/usr/share/hello-php-world /var/lib/hello-php-world

syntaxcheck:
	rv=0; find ${DIRS} -name '*.php' -print0 |& while IFS= read -p -d '' -r; do \
		php -l "$$REPLY" | grep -v '^No syntax errors detected in '; \
		(( PIPESTATUS[0] )) && rv=1; \
	done; exit $$rv

.PHONY: all syntaxcheck