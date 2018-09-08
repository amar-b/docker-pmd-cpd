### Build image
```
docker build -t code-analysis .
```

### PMD
- Static code analysis (for Java & Apex)

Basic java example:
```
docker run --rm -it -v "$(pwd)":/workdir code-analysis pmd -d ./ -R java-basic
```

### CPD 
- Duplicate code checking using the Rabin–Karp string search algorithm 
- CPD works with Java, JSP, C, C++, Fortran, PHP, and C# code.

Example usage:
```
docker run --rm -it -v "$(pwd)":/workdir code-analysis cpd --minimum-tokens 100 --files ./ 
```
