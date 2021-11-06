HashcatRulesEngine
====================

A stand-alone implementation of [Hashcat's](https://github.com/hashcat/hashcat) rule engine, based on John the Ripper's rule engine.  
Implements rule parsing separate from rule application for better performance and better detection of duplicate rules.

### Build

```bash
$ make
```


### Usage

```
USAGE:  ./hcre  rule_file  [rule_file  ...]

Input words are read from STDIN, mangled words are written on STDOUT
All rule files are unioned together and duplicate rules are removed
For a cross product of rules, pipe this program into another instance of itself
```

Get the rules from hashcat `rules/` directory.
    
### Example

```bash
# From a wordlist
$ echo "password
secret" > words.txt
$ ./hcre best64.rule < words.txt

# From stdin
$ echo password | ./hcre  leetspeak.rule  combinator.rule
```
