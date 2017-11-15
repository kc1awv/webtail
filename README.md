
webtail
=======

[![GoCard][1]][2]
[![GitHub license][3]][4]

[1]: https://goreportcard.com/badge/LeKovr/webtail
[2]: https://goreportcard.com/report/github.com/LeKovr/webtail
[3]: https://img.shields.io/badge/license-MIT-blue.svg
[4]: LICENSE

[webtail](https://github.com/LeKovr/webtail) - Tail [log]files via websocket

This service loads list of logfiles from directory tree & continuously shows result of chosen file tail via websocket.

## Install

```
go get github.com/LeKovr/webtail
```

### Download binary

See [Latest release](https://github.com/LeKovr/webtail/releases/latest)

### Docker

```
docker pull lekovr/webtail
```

See [docker-compose.yml](docker-compose.yml) for usage example.

## Note about gorilla/websocket

Not choosen because [Connections support one concurrent reader and one concurrent writer](https://godoc.org/github.com/gorilla/websocket).
But we need two writers (one for tail and one for command responses). May be we join these writers in future.

## TODO

* [x] js: don't enable "follow" button on big update
* [x] go: use https://github.com/hpcloud/tail instead https://github.com/LeKovr/tail
* [ ] js: add inputs for filter plain/green/yellow/red
* [ ] js: reconnect ws on close
* [ ] add text field for log filtering

## License

The MIT License (MIT), see [LICENSE](LICENSE).

Copyright (c) 2016-2017 Alexey Kovrizhkin <lekovr+webtail@gmail.com>
