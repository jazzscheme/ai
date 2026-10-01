# Project toplevel files

.buildini
.configurations
.jaz
.jazini
.project
.repository
INSTALL
NEWS
README
build\
  stable\
    jedi.app
configure
deploy
jaz
jazz\
  lib\
    jazz.sample\
      .package
      src\
        jazz\
          sample\
            module.jazz
lib\
makefile

# File: .buildini
```
;;;==============
;;;  JazzScheme
;;;==============
;;;
;;;; Local buildini
;;;


(jazz:jazz-repository "jazz")
(jazz:repositories ".")
```

# File: .configurations
```
(name: test   safety: develop optimize?: #f debug-environments?: #t debug-location?: #t debug-source?: #f debug-foreign?: #f mutable-bindings?: #f kernel-interpret?: #f destination: "binaries/test"  features: (test)   properties: (binaries?: #t))
(name: stable safety: develop optimize?: #f debug-environments?: #t debug-location?: #t debug-source?: #f debug-foreign?: #f mutable-bindings?: #f kernel-interpret?: #f destination: "build/stable"   features: (stable) properties: ())
(name: stage  safety: develop optimize?: #f debug-environments?: #t debug-location?: #t debug-source?: #f debug-foreign?: #f mutable-bindings?: #f kernel-interpret?: #f destination: "binaries/stage" features: (stage)  properties: (binaries?: #t))
(name: prod   safety: develop optimize?: #f debug-environments?: #t debug-location?: #t debug-source?: #f debug-foreign?: #f mutable-bindings?: #f kernel-interpret?: #f destination: "binaries/prod"  features: (prod)   properties: (binaries?: #t))
```

# File: .jaz
```
export GAMBITDIR=/usr/local/Gambit
export JAZCONF=stable
export JAZDEST=build/stable
```

# File: .jazini
```
;;;==============
;;;  JazzScheme
;;;==============
;;;
;;;; Local jazini
;;;


(jazz:default-safety 'release)
(jazz:default-target 'jedi)
```

# File: .project
```
;;;==============
;;;  JazzScheme
;;;==============
;;;
;;;; Project
;;;


(data jazz.ide.data.project


(import (jazz.project)
        (jazz.editor.jazz))


(form
  (<Project> name: jedi description-file: {File :context ".repository"} active-project: Jedi depot-directory: {Directory :context}
    (<*>                tag-reference: {File :context "lib" "jedi" "jedi.project"})
    (<*>                tag-reference: {File :context "jazz" ".project"})
    (<*>                tag-reference: {File :context "lib" ".project"}))))
```

# File: .repository
```
(repository Jedi

  (library "lib"))
```

# File: configure
```
#!/bin/sh

echo 'Jedi does not use the ./configure and make build process.'
echo 'See INSTALL for details and start the build system with ./jam.'
```

# File: makefile
```
all:
        @echo 'Jedi does not use the ./configure and make build process.'
        @echo 'See INSTALL for details and start the build system with ./jam.'
```
