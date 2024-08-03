# APK

### Alpine Package Keeper (APK) Command Line Interface (CLI)

APK is the package manager used by Alpine Linux. Below is an extensive list of APK commands, covering basic, intermediate, and advanced usage.

#### Basic Commands

- **Update the package list:**
  ```sh
  apk update
  ```

- **Install a package:**
  ```sh
  apk add package_name
  ```

- **Remove a package:**
  ```sh
  apk del package_name
  ```

- **Search for a package:**
  ```sh
  apk search package_name
  ```

- **List all installed packages:**
  ```sh
  apk info
  ```

- **Get information about a specific package:**
  ```sh
  apk info package_name
  ```

- **Upgrade all installed packages:**
  ```sh
  apk upgrade
  ```

#### Intermediate Commands

- **Install a package without dependencies:**
  ```sh
  apk add --no-cache package_name
  ```

- **Add a virtual package:**
  ```sh
  apk add --virtual virtual_name package_name
  ```

- **Remove a virtual package:**
  ```sh
  apk del virtual_name
  ```

- **List all available versions of a package:**
  ```sh
  apk search -v package_name
  ```

- **List installed packages with detailed information:**
  ```sh
  apk info -vv
  ```

- **Show dependencies of a package:**
  ```sh
  apk info --depends package_name
  ```

- **Show reverse dependencies of a package:**
  ```sh
  apk info --rdepends package_name
  ```

#### Advanced Commands

- **Clean the cache:**
  ```sh
  apk cache clean
  ```

- **Enable a repository:**
  ```sh
  echo "http://dl-cdn.alpinelinux.org/alpine/edge/community" >> /etc/apk/repositories
  ```

- **Disable a repository:**
  ```sh
  sed -i '/edge\/community/d' /etc/apk/repositories
  ```

- **Pin a package version:**
  ```sh
  apk add package_name=version
  ```

- **Hold a package to prevent updates:**
  ```sh
  apk add package_name --no-upgrade
  ```

- **Allow downgrading a package:**
  ```sh
  apk add package_name --allow-downgrade
  ```

- **Install a package from a specific repository:**
  ```sh
  apk add package_name@repository
  ```

- **List orphaned packages:**
  ```sh
  apk info -r
  ```

- **Remove orphaned packages:**
  ```sh
  apk del $(apk info -r)
  ```

- **Rebuild the repository index:**
  ```sh
  apk index -o /path/to/index.tar.gz /path/to/packages
  ```

- **Install a package from a local file:**
  ```sh
  apk add /path/to/package.apk
  ```

- **Create a local package repository:**
  ```sh
  mkdir -p /path/to/repo
  cp /path/to/package.apk /path/to/repo/
  apk index -o /path/to/repo/x86_64/APKINDEX.tar.gz /path/to/repo/*.apk
  ```

- **Verify package integrity:**
  ```sh
  apk verify package_name
  ```

- **Fix broken dependencies:**
  ```sh
  apk fix
  ```

- **Enable verbose output:**
  ```sh
  apk add -v package_name
  ```

- **Force a package installation:**
  ```sh
  apk add --force package_name
  ```

- **Simulate package installation:**
  ```sh
  apk add --simulate package_name
  ```

- **List all available commands and options:**
  ```sh
  apk --help
  ```

### Summary

This comprehensive list covers a wide range of APK commands for Alpine Linux, from basic package management to more advanced techniques for handling repositories, dependencies, and package integrity. Whether you're managing a small system or a large infrastructure, these commands provide a robust toolkit for maintaining your Alpine Linux environment.
