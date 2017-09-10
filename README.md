malice-avg
==========

[![Circle CI](https://circleci.com/gh/malice-plugins/avg.png?style=shield)](https://circleci.com/gh/malice-plugins/avg) [![License](http://img.shields.io/:license-mit-blue.svg)](http://doge.mit-license.org) [![Docker Stars](https://img.shields.io/docker/stars/malice/avg.svg)](https://hub.docker.com/r/malice/avg/) [![Docker Pulls](https://img.shields.io/docker/pulls/malice/avg.svg)](https://hub.docker.com/r/malice/avg/) [![Docker Image](https://img.shields.io/badge/docker%20image-658MB-blue.svg)](https://hub.docker.com/r/malice/avg/)

This repository contains a **Dockerfile** of [avg](http://www.avg.net/lang/en/) for [Docker](https://www.docker.io/)'s [trusted build](https://index.docker.io/u/malice/avg/) published to the public [DockerHub](https://index.docker.io/).

### Dependencies

-	[debian:jessie (*125 MB*\)](https://index.docker.io/_/debian/)

### Installation

1.	Install [Docker](https://www.docker.io/).
2.	Download [trusted build](https://hub.docker.com/r/malice/avg/) from public [DockerHub](https://hub.docker.com): `docker pull malice/avg`

### Usage

```
docker run --rm malice/avg EICAR
```

#### Or link your own malware folder:

```bash
$ docker run --rm -v /path/to/malware:/malware:ro malice/avg FILE

Usage: avg [OPTIONS] COMMAND [arg...]

Malice AVG AntiVirus Plugin

Version: v0.1.0, BuildTime: 20170122

Author:
  blacktop - <https://github.com/blacktop>

Options:
  --verbose, -V         verbose output
  --table, -t	       output as Markdown table
  --callback, -c	    POST results to Malice webhook [$MALICE_ENDPOINT]
  --proxy, -x	       proxy settings for Malice webhook endpoint [$MALICE_PROXY]
  --timeout value       malice plugin timeout (in seconds) (default: 60) [$MALICE_TIMEOUT]    
  --elasitcsearch value elasitcsearch address for Malice to store results [$MALICE_ELASTICSEARCH]   
  --help, -h	        show help
  --version, -v	     print the version

Commands:
  update	Update virus definitions
  web       Create a AVG scan web service  
  help		Shows a list of commands or help for one command

Run 'avg COMMAND --help' for more information on a command.
```

Sample Output
-------------

### JSON:

```json
{
    "avg": {
        "infected": true,
        "result": "Virus identified EICAR_Test",              
        "engine": "13.0.3114",
        "database": "4477/13807",        
        "updated": "20170121"
    }
}
```

### Markdown Table:

---

#### AVG

| Infected | Result                      | Engine    | Updated  |
|----------|-----------------------------|-----------|----------|
| true     | Virus identified EICAR_Test | 13.0.3114 | 20170122 |

---

Documentation
-------------

-	[To write results to ElasticSearch](https://github.com/malice-plugins/avg/blob/master/docs/elasticsearch.md)
-	[To create a AVG scan micro-service](https://github.com/malice-plugins/avg/blob/master/docs/web.md)
-	[To post results to a webhook](https://github.com/malice-plugins/avg/blob/master/docs/callback.md)
-	[To update the AV definitions](https://github.com/malice-plugins/avg/blob/master/docs/update.md)

### Issues

Find a bug? Want more features? Find something missing in the documentation? Let me know! Please don't hesitate to [file an issue](https://github.com/malice-plugins/avg/issues/new).

### CHANGELOG

See [`CHANGELOG.md`](https://github.com/malice-plugins/avg/blob/master/CHANGELOG.md)

### Contributing

[See all contributors on GitHub](https://github.com/malice-plugins/avg/graphs/contributors).

Please update the [CHANGELOG.md](https://github.com/malice-plugins/avg/blob/master/CHANGELOG.md) and submit a [Pull Request on GitHub](https://help.github.com/articles/using-pull-requests/).

### License

MIT Copyright (c) 2016-2017 **blacktop**
