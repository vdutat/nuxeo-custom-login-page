# nuxeo-custom-login-page

## About / Synopsis

This plugin demonstrates how to override the **login page**.

It was generated with the following commands:
```
mkdir nuxeo-custom-login-page && cd $_
nuxeo bootstrap multi-module seam
mkdir -p nuxeo-custom-login-page-jsf/src/main/resources/web/nuxeo.war && cd $_
wget https://github.com/nuxeo/nuxeo/raw/2023/modules/platform/nuxeo-platform-web-common/src/main/resources/web/nuxeo.war/login.jsp
# MODIFY login.jsp
# MODIFY deployment-fragment.xml (add '<require>org.nuxeo.ecm.platform.web.common</require>` inside `fragment` tag)
cd -
nuxeo bootstrap package
nuxeo bootstrap docker
nuxeo bootstrap docker-compose
```

## Requirements

Building requires the following software:

* git
* maven
* docker (only for **Option 1** below)
* docker-compose (only for **Option 1** below)

## Build

```
git clone ...
cd nuxeo-custom-login-page

mvn clean install
```

if you don't want to build the **Docker** image, use:
```
mvn clean install -DskipDocker
```

## Installation

### Option 1 (using the Docker image)

```
docker-compose up -d ; docker-compose logs -f ; docker-compose down -v
```

### Option 2

```
nuxeoctl mp-install nuxeo-custom-login-page/nuxeo-custom-login-page-package/target/nuxeo-custom-login-page-package-*.zip
```

## Support

**These features are not part of the Nuxeo Production platform, they are not supported**

These solutions are provided for inspiration and we encourage customers to use them as code samples and learning resources.

This is a moving project (no API maintenance, no deprecation process, etc.) If any of these solutions are found to be useful for the Nuxeo Platform in general, they will be integrated directly into platform, not maintained here.


## License

[Apache License, Version 2.0](http://www.apache.org/licenses/LICENSE-2.0.html)

## About Nuxeo

Nuxeo Platform is an open source Content Services platform, written in Java. Data can be stored in both SQL & NoSQL databases.

The development of the Nuxeo Platform is mostly done by Nuxeo employees with an open development model.

The source code, documentation, roadmap, issue tracker, testing, benchmarks are all public.

Typically, Nuxeo users build different types of information management solutions for [document management](https://www.nuxeo.com/solutions/document-management/), [case management](https://www.nuxeo.com/solutions/case-management/), and [digital asset management](https://www.nuxeo.com/solutions/dam-digital-asset-management/), use cases. It uses schema-flexible metadata & content models that allows content to be repurposed to fulfill future use cases.

More information is available at [www.nuxeo.com](https://www.nuxeo.com).

