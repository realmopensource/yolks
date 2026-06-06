# Yolks

A curated collection of core Docker images for Realm's egg system. Each image is rebuilt periodically to keep
dependencies up to date.

Images are published to `ghcr.io/realmopensource` under the `yolks`, `games`, and `installers` namespaces. The
following logic determines which namespace an image uses:

* `oses` — base images with core packages to get you started.
* `games` — images in the `games` folder, built for running a specific game or type of game.
* `installers` — images in the `installers` directory, used by egg install scripts rather than running servers.
  They pre-install common tools like `curl` and `wget` to speed up installations.
* `yolks` — generic runtime images (Java, Node.js, Python, Go, etc.) that eggs can swap between.

All images support `linux/amd64` and `linux/arm64` unless otherwise noted. On arm64 nodes, use the same tag — no
extra configuration is required.

## Contributing

When adding a new version to an existing image, such as `java v42`, add it under a child folder of `java` — for
example `java/42/Dockerfile`. Update the matching `.github/workflows` file so the new version is tagged correctly.

## Available Images

* [`base oses`](/oses)
  * [`alpine`](/oses/alpine)
    * `ghcr.io/realmopensource/yolks:alpine`
  * [`debian`](/oses/debian)
    * `ghcr.io/realmopensource/yolks:debian`

* [`games`](/games)
  * [`rust`](/games/rust)
    * `ghcr.io/realmopensource/games:rust`
  * [`source`](/games/source)
    * `ghcr.io/realmopensource/games:source`
  * [`hytale`](/games/hytale)
    * `ghcr.io/realmopensource/games:hytale`
  * [`conan_exiles`](/games/conan_exiles)
    * `ghcr.io/realmopensource/games:conan_exiles`

* [`golang`](/go)
  * [`go1.14`](/go/1.14) — `ghcr.io/realmopensource/yolks:go_1.14`
  * [`go1.15`](/go/1.15) — `ghcr.io/realmopensource/yolks:go_1.15`
  * [`go1.16`](/go/1.16) — `ghcr.io/realmopensource/yolks:go_1.16`
  * [`go1.17`](/go/1.17) — `ghcr.io/realmopensource/yolks:go_1.17`
  * [`go1.18`](/go/1.18) — `ghcr.io/realmopensource/yolks:go_1.18`
  * [`go1.19`](/go/1.19) — `ghcr.io/realmopensource/yolks:go_1.19`
  * [`go1.20`](/go/1.20) — `ghcr.io/realmopensource/yolks:go_1.20`
  * [`go1.21`](/go/1.21) — `ghcr.io/realmopensource/yolks:go_1.21`
  * [`go1.22`](/go/1.22) — `ghcr.io/realmopensource/yolks:go_1.22`
  * [`go1.23`](/go/1.23) — `ghcr.io/realmopensource/yolks:go_1.23`
  * [`go1.24`](/go/1.24) — `ghcr.io/realmopensource/yolks:go_1.24`
  * [`go1.25`](/go/1.25) — `ghcr.io/realmopensource/yolks:go_1.25`
  * [`go1.26`](/go/1.26) — `ghcr.io/realmopensource/yolks:go_1.26`, `ghcr.io/realmopensource/yolks:go_latest`

* [`java`](/java)
  * `ghcr.io/realmopensource/yolks:java_8`, `java_8j9`, `java_11`, `java_11j9`, `java_16`, `java_16j9`
  * `java_17`, `java_17j9`, `java_18`, `java_18j9`, `java_19`, `java_19j9`
  * `java_21`, `java_22`, `java_23`, `java_24`, `java_25`

* [`nodejs`](/nodejs)
  * `ghcr.io/realmopensource/yolks:nodejs_12` through `nodejs_20`

* [`python`](/python)
  * `ghcr.io/realmopensource/yolks:python_3.7` through `python_3.11`

### Installation Images

* `ghcr.io/realmopensource/installers:alpine`
* `ghcr.io/realmopensource/installers:debian`

## Attribution

Derived from the [Pterodactyl yolks](https://github.com/pterodactyl/yolks) project. Until Realm images are published,
eggs can continue using `ghcr.io/pterodactyl/yolks` as a fallback.
