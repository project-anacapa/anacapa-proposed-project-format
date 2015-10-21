# anacapa-proposed-project-format
In submit.cs, project config was in database.  We propose to do it in github repo.


In THIS repo, each subdirectory represents what the TOP level might look like in a project repo.   

The very level has a subdirectory for each proposed structure, e.g.

```
 proposal1
 proposal2
 etc.
```

The next level will be a directory for each course in the current set of courses

e.g
. 
```
 cs32_s15
 cs32_f15
 etc.
```

The next level will be each project in that course, e.g.

```
 lab00
 lab01
 lab02
 etc.
```

At the next level, we finally have an honest to goodness project---this the level that would be the TOP level in a github repo that contains a project description.

In the top level directory, we'll have 

```
Makefile
build_files
execution_files
expected_files.json
testables
```

Under build_files and execution_files, we have the actual contents of the files that are copied either into the build or the execution environment.   

* build_files are typically the parts of the code that are instructor supplied, and that DO NOT CHANGE in a student submission.   
* execution_files might include data files that are part of a test, which must be in the execution environment (i.e. the current directory) when the test is run.

expected_files.json is an object that contains one property for each file that we expect.   The value of each of those properties is itself an object with the following properties:

```

```

Under testables, we have a folder for each testable, e.g. 

```
helloWorld
lab00Test
```

Each of those contains the following:

```
index.json
```

The index.json file will contain an object with the following properties.  Note that 

* certain properties may be absent, in which case a default value is assumed:
* for build_files, execution_files, expected_files, the default is "all".
* for build_files, execution_files, expected_files, legal values are "all", "none", or an array of strings representing filenames.  Those filenames MUST be present in the 


```json

{
   "build_files" : "all", /* could be "all", "none", or an array of filenames, e.g. ["file1.cpp","file2.cpp"]

}

```


