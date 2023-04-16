Portformat

The portformat package is a Go library for parsing strings of port numbers and ranges. It provides a simple interface for converting strings to slices of integers.
Installation

To install portformat, use go get:

arduino

go get github.com/<username>/portformat

Usage

go

package main

import (
	"fmt"
	"github.com/<username>/portformat"
)

func main() {
	ports, err := portformat.PortsFromString("80,443,8080-8081")
	if err != nil {
		panic(err)
	}
	fmt.Println(ports)
}

Output:

yaml

[80 443 8080 8081]

Functionality

The PortsFromString function parses a string of port numbers and ranges separated by commas and/or dashes and returns a slice of integers. For example, "80,443,8080-8081" would be parsed as the slice [80, 443, 8080, 8081].
Limitations

The PortsFromString function only supports port numbers in the range of 1-65535. If a port number outside of this range is provided, an error will be returned. Additionally, the function assumes that the input string is well-formed and may panic or return incorrect results if the input is malformed.
Contributing

Contributions to portformat are welcome! Please submit a pull request with your changes.
