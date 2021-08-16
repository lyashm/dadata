# Client for DaData.ru

Forked from https://github.com/webdeskltd/dadata.


[![Build Status](https://travis-ci.org/lyashm/dadata.svg)](https://travis-ci.org/lyashm/dadata)
[![GitHub release](https://img.shields.io/github/release/lyashm/dadata.svg)](https://github.com/lyashm/dadata/releases)
[![Go Report Card](https://goreportcard.com/badge/github.com/lyashm/dadata)](https://goreportcard.com/report/github.com/lyashm/dadata)
[![GoDoc](https://godoc.org/github.com/lyashm/dadata?status.svg)](https://godoc.org/github.com/lyashm/dadata)

DaData API v2

Implemented [Clean](https://dadata.ru/api/clean/) and [Suggest](https://dadata.ru/api/suggest/) methods.

## Installation

`go get github.com/lyashm/dadata`

## Usage
```go
import (
	"context"
	"fmt"

	"github.com/lyashm/dadata/v2"
	"github.com/lyashm/dadata/v2/api/suggest"
)

func DaDataExample()  {
	api := dadata.NewSuggestApi()

	params := suggest.RequestParams{
		Query: "ул Свободы",
	}

	suggestions, err := api.Address(context.Background(), &params)
	if err != nil {
		return
	}

	for _, s := range suggestions {
		fmt.Printf("%s", s.Value)
	}
}
```

## Licence
MIT see [LICENSE](LICENSE)
