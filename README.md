rdfconvert
==========

A little python script that converts files and whole directory trees from one RDF serialization into another.

```
usage: rdfconvert.py [-h] --from
                     {json-ld,trix,ttl,application/rdf+xml,nquads,xml,text/html,rdf-json,rdfa,n3,nt}
                     [--from-ext FROM_EXT [FROM_EXT ...]] [-R]
                     [-o [OUTPUTDIR]] --to
                     {xml,json-ld,trix,pretty-xml,ttl,nquads,n3,nt,rdf-json}
                     [--to-ext TO_EXT] [-f] [-n] [-s] [-v]
                     INPUT [INPUT ...]

Convert one RDF serialization into another.

This script allows you to convert several files at once. It can 
convert individual files or even whole directory trees at once 
(with or without preserving the directory tree structure).
    

positional arguments:
  INPUT                 A list of input files or input directories. When
                        *files* are specified, they will be parsed and
                        converted regardless of their extension. But when
                        *directories* are specified, the script will try to
                        find files inside these directories that match certain
                        extensions (either all default extensions for the
                        input format as specified by the --from flag, or the
                        custom extension(s) as specified directly by the
                        --from-ext flag). Input directories may be searched
                        recursively via the -R flag.

optional arguments:
  -h, --help            show this help message and exit
  --from {json-ld,trix,ttl,application/rdf+xml,nquads,xml,text/html,rdf-json,rdfa,n3,nt}
                        The serialization format of the input files to
                        convert.
  --from-ext FROM_EXT [FROM_EXT ...]
                        The file extensions to match when browsing input
                        directories (could be .owl, .xml, .n3, .jsonld, .rdf,
                        ...). You only have to provide this flag if you're
                        unhappy with the default extensions for the given
                        input format. You can view these default extensions at
                        the end of this help.
  -R, --recursive       When input directories are given, browse them
                        recursively to find and convert files.
  -o [OUTPUTDIR]        The directory to write the output files (omit this
                        flag to print the output to the stdout).
  --to {xml,json-ld,trix,pretty-xml,ttl,nquads,n3,nt,rdf-json}
                        The serialization format of the output.
  --to-ext TO_EXT       The file extension of the output files that will be
                        created (could be .owl, .xml, .n3, .jsonld, .rdf,
                        ...). You only have to provide this flag if you're
                        unhappy with the default extension for the given
                        output format. You can view these default extensions
                        at the end of this help. When the -o flag is not
                        specified, the output will be written the the stdout
                        instead of files, so the --to-ext flag will have no
                        effect. Don't forget to add a dot (.) in front of the
                        extension name (so provide .foo instead of foo).
  -f, --force           Always overwrite existing output files, instead of
                        prompting.
  -n, --no-tree         When given in combination with -R (recursive input
                        file matching), all output files will be written in
                        the same "flat" directory. Without this -n flag, the
                        same directory structure of the input directory will
                        be created (if necessary) and the output files will be
                        written to the corresponding directories of where they
                        were found in the input directories. Only those output
                        directories will be created for the input directories
                        that contain at least one matching input file. If you
                        specify this flag, all output files will be stored in
                        the same directory and you may run into filename
                        collisions!
  -s, --simulate        Do not write any output files, but just print a
                        message for each file that they *would* be written
                        without the -s flag.
  -v, --verbose         Verbosely print some debugging info.

Default extensions for INPUT format:
 - json-ld             : ['.jsonld', '.json-ld']
 - trix                : ['.xml', '.trix']
 - ttl                 : ['.ttl']
 - application/rdf+xml : ['.xml', '.rdf', '.owl']
 - nquads              : ['.nq']
 - xml                 : ['.xml', '.rdf', '.owl']
 - text/html           : ['.html']
 - rdf-json            : ['.json']
 - rdfa                : ['.xhtml', '.html']
 - n3                  : ['.n3']
 - nt                  : ['.nt']

Default extension for OUTPUT format:
 - xml        : '.xml'
 - json-ld    : '.jsonld'
 - trix       : '.xml'
 - pretty-xml : '.xml'
 - ttl        : '.ttl'
 - nquads     : '.nq'
 - n3         : '.n3'
 - nt         : '.nt'
 - rdf-json   : '.json'
```
