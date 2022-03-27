# muwire-filter

Search term filters and warnings for MuWire.  For the rationale behind these filters check [this GitHub issue](https://github.com/zlatinb/muwire/issues/127)

### Filter definition

This project contains keyword filters and associated warnings.  A filter consists of the following:

1. A `terms.csv` file of the format `keyword,jurisdiction`.  The key `ALL_JURISDICTIONS` is reserved for the translateable string "All Jurisdictions".
2. A `url.txt` file containing a link to the community managing this filter.  In the example it is a link to this GitHub repo.
3. A `warning.txt` file which contains the warning to be displayed to the user should they try to search for a term in the terms list.  In English.
4. One or more `warning_XX.txt` files containing the warning translated in another locale where XX stands for the locale code.
5. A `version.txt` file which is used by the build system to generate an artifact and upload it to a maven repository.


### Building

Currently the filter artifacts are uploaded to the local maven repository.  To build and deploy the example filter, you need to have a Java Development Kit (JDK) installed on your machine.  Then, from a terminal window or command prompt, type:

```
./gradlew publish
```

That should succeed quickly.  To verify if it worked, check `$HOME/.m2/repository/com/muwire/filters` directory.  Inside you will find the "example" artifact published as a zip.

### Future work

A maven repository that is accessible by the public needs to be set up and the build script updated to publish to that repository.
