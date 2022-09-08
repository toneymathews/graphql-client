# Changelog
All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [0.18.1] - 2022-09-08

### Changed
- Fix `as_json` and `to_json`. `0.17.0` breaks `as_json`/`to_json` on graphql response because now `ObjectClass` class has `definer` variable that has circular references and ActiveSupport(`as_json`) tries to call `instance_values` if `object` doesn't have `to_hash` method.

`response.data.instance_values["definer"].instance_values["klass"].instance_values["null_type"].instance_values["of_klass"].instance_values["null_type"].instance_values["of_klass"]`

To fix this, `to_hash` alias method was added to the relevant classes. This allows ActiveSupport to handle `as_json` / `to_json` without referencing internal variables. There are already `to_h` methods to return `original_hash` or `data` in several classes so this the fix just added the alias to that.


## [0.18.0] - 2022-09-07
- This project was forked from https://github.com/github/graphql-client because it became unmaintained and it had open issues that needed to be fixed.