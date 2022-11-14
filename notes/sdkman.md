# SDKMAN!

<https://sdkman.io>

Manages parallel versions of SDKs on most Unix-based systems. Provides CLI and API for installing, switching, removing, and listing **Candidates**.

Manages JVM SDKs like Java, Scala, Kotlin, etc. Also supports Ant, Gradle, Grails, Maven, Spring Boot, and others.

## Install

```sh
curl -s "https://get.sdkman.io" | zsh
source "$HOME/.sdkman/bin/sdkman-init.sh"
```

Adds couple lines to end of **.bash_profile**. Must be at end to work.

### Version

```sh
sdk version
```

### Self-Update

```sh
sdk selfupdate
```

Force re-installation:

```sh
sdk selfupdate force
```

## SDK Management

### Install Latest Stable

```sh
sdk install java
```

### Install Specific Version

```sh
sdk install scala 3.2.0
```

### Link Local Version

If have local version, can specify name and path to link to it:

```sh
sdk install groovy 3.0.0-SNAPSHOT /path/to/groovy-3.0.0-SNAPSHOT
```

 local version name (`3.0.0-SNAPSHOT` in ex) must be unique from list of available names.

### Remove Version

```sh
sdk uninstall scala 3.1.3
```

Removing local version won't remove installation.

### List Candidates

#### All

```sh
sdk list
```

#### List Candidate Versions

```sh
sdk list java
```

### Use Version

```sh
sdk use kotlin 1.7.21
```

For current shell only. To make change permanent, use **default**.

### Default Version

```sh
sdk default kotlin 1.7.0
```

### Current Version

Single candidate:

```sh
sdk current java
```

All candidates:

```sh
sdk current
```

### Upgrade Version

Single candidate:

```sh
sdk upgrade gradle
```

All candidates:

```sh
sdk upgrade
```

## Broadcast Messages

Latest SDK release notifications:

```sh
sdk broadcast
```

## Update

Periodically SDKMAN! requires refresh to become aware of new (or removed) candidates. When candidate metadata has potentially grown stale, warning is displayed (“WARNING: SDKMAN is out-of-date and requires an update.”). Refresh candidate cache:

```sh
sdk update
```

## Flush

If need to flush local state:

```sh
sdk flush archives # cache of downloaded binaries; can take up space, worth it periodically
sdk flush broadcast
sdk flush temp # temp folder
```

## Config

Found in `~/.sdkman/etc/config`.
