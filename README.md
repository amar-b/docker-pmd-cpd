# docker-pmd-cpd

Builds a docker image for [PMD](https://pmd.github.io/)

PMD is a source code analyzer. It supports Java, JavaScript, and Salesforce Apex/Visualforce. 

CPD is a copy-paste detector. It finds duplicated code in Java, C, C++, C# Python, JavaScript, Fortran, PHP, among others.

The image built currently uses version of 6.7.0 of PMD/CPD as of 2nd September 2018. 

Contains the dockerfile for building an image for source code analysis (PMD) and duplicate code detection (CPD)

### Build image
```
docker build -t code-analysis .
```

### PMD
- Static code analysis (for Java & Apex)
- Rule references can be found [here](https://pmd.github.io/pmd-6.7.0/tag_rule_references.html)
- CLI reference can be found [here](https://pmd.github.io/pmd-6.7.0/pmd_userdocs_cli_reference.html)
Java example:
```
docker run --rm -it -v "$(pwd)":/workdir code-analysis pmd -d ./ -R category/java/errorprone.xml/UnconditionalIfStatement
```

### CPD 
- Duplicate code checking using the Rabin–Karp string search algorithm 
- CPD works with Java, JSP, C, C++, Fortran, PHP, and C# code.
Example usage:
```
docker run --rm -it -v "$(pwd)":/workdir code-analysis cpd --minimum-tokens 100 --files ./ 
```


