#! /usr/bin/env gmake

all: script.sh config.json

script.sh: command/atp
	command/atp script | tee script.sh

config.json: command/atp config/template.json
	command/atp config | tee config.json | jq .

clean:
	rm -f script.sh config.json

run: script.sh config.json
	sh script.sh config.json

.PHONY: run
