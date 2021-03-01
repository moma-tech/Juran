## Remove File Already Tracked

- git rm -r -n --cached "file"
- -r : recursion
- -n : dry-run, for checking & not perform the op
- -f : force
- --quite : no output
- --cached: only remove stashed from index, file will not del

```
[ivan@day103 resources]$ git rm -r -n --cached application-prod.yml
rm 'm64-fund/src/main/resources/application-prod.yml'
[ivan@day103 resources]$

```

## Set into ignore

- edit .gitignore

```
### Prod Setting ###
/m64-fund/src/main/resources/application-prod.yml
```
