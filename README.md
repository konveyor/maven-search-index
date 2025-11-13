# Maven Central Index

This repository provides a way to build a fixed version of the `nexus-maven-repository-index.gz` Maven Central Index (ref. [Central Index](https://maven.apache.org/repository/central-index.html#central-index)) without `module` and `pom.512` files but with the right JAR files inside.

##  Requirements
- Java 8 installed
- Maven installed
- 32GB RAM, ideally 64GB RAM
- 10GB disk space

## How to build
1. Clone this repo: `git clone https://github.com/konveyor/maven-search-index.git`
2. Move into the directory: `cd maven-search-index`
3. Install parent pom: `mvn -B -N install -f pom.xml`
4. Install indexer pom: `mvn -B install -f indexer/pom.xml`
5. Generate index: `mvn -f data-text/pom.xml clean compile package -DskipTests`
6. Move into the directory: `maven-search-index/data-text/target`

Two files will be generated in `data-text/target`:
- The data file: `central.archive-metadata.txt`
- The index file: `central.archive-metadata.idx`
