go-bitset is an efficient implementation of a map between unsigned, 32-bit or
64-bit integers and boolean values. It provides methods for setting, clearing,
flipping, and testing individual integers.

go-bitset also provides set intersection, union, difference, complement, and
symmetric operations, as well as tests to check whether any, all, or no bits
are set, and the ability to query the bitset's length and number of set bits.

Bitsets are expanded automatically to the size of the largest bit set.

== Installation

go get github.com/hewenyu/go-bitset

== Documentation

go doc github.com/pmylund/go-bitset
or http://go.pkgdoc.org/github.com/hewenyu/go-bitset

== Usage

import "github.com/pmylund/go-bitset"

b := bitset.New32(10000)
b.Set(1000)
if b.Test(1000) {
	fmt.Println("Bit 1000 is set!")
}
b.Clear(1000)
b.Set(10)

ob := bitset.New32(0)
// ob expands automatically
ob.Set(10)

if b.Intersection(ob).Count() > 1 {
	fmt.Println("The two sets intersect!")
}

oob := bitset.New64(0)
oob.Set(1000000000)

go-bitset is based on bitset by Will Fitzgerald.
