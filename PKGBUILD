#!/bin/bash

# Created from the original PKGBUILD by Caleb Maclennan <caleb@alerque.com> and Florian Bruhin (The Compiler) <archlinux.org@the-compiler.org>

# Disable various shellcheck rules that produce false positives in this file.
# Repository rules should be added to the .shellcheckrc file located in the
# repository root directory, see https://github.com/koalaman/shellcheck/wiki
# and https://archiv8.github.io for further information.
# shellcheck disable=SC2034,SC2154
# ToDo: Add files: User documentation
# ToDo: Add files: Tooling
# FixMe: Namcap warnings and errors

# Maintainer: Ross Clark <https://github.com/Archiv8/python-strictyaml/discussions>
# Contributor: Ross Clark <https://github.com/Archiv8/python-strictyaml/discussions>

_langname="python"
_relname="strictyaml"

pkgname="${_langname}-${_relname}"
pkgver=1.6.1
pkgrel=1
pkgdesc='A type-safe YAML parser that parses a restricted subset of the YAML specificaton'
arch=(
  "any"
)
url="http://hitchdev.com/strictyaml"
license=(
  "MIT"
)
depends=(
  "python"
  "python-dateutil"
  "python-ruamel-yaml"
)
makedepends=(
  "python-setuptools"
)
_tarname="${_relname}-$pkgver"
source=(
  "https://files.pythonhosted.org/packages/source/${_relname::1}/${_relname}/${_tarname}.tar.gz"
)
sha512sums=(
  '1c699e3aad88d3ca6a2f67b46b83f8a4e09410b2bdaebd623e2b21c173b97cc7301387d305fff3251c48d680c3fadb0879b2d313e869beadf509535de358c292'
)

build() {

  cd "${_tarname}"

  python setup.py build
}

package() {

  cd "$_tarname"
  python setup.py install --root="${pkgdir}" --optimize=1 --skip-build

  install -Dm0644 -t "${pkgdir}/usr/share/licenses/${pkgname}/" LICENSE.txt
}
