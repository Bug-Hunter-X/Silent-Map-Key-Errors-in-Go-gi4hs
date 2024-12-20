# Silent Map Key Errors in Go

This example demonstrates a potential issue in Go where accessing a non-existent key in a map returns the zero value for the map's value type without causing a panic or error. This can lead to hard-to-debug errors if not handled carefully.

## The Problem

In many languages, accessing a non-existent key in a map or dictionary would throw an exception or return an error. However, in Go, accessing a non-existent key simply returns the zero value for the value type associated with the map.  For example, if the map's value type is `int`, accessing a missing key will return `0`. If it's a string, it will return an empty string. This behavior, while often convenient, can also be a source of subtle bugs because there's no clear indication that the key is missing. 

## Solution

The best way to avoid issues is to explicitly check if a key exists using the `len` function or the `ok` value from a comma ok idiom before using it.
