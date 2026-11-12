# Package hierarchy

jazz.sample\
  .package
  src\
    jazz\
      sample\
        module.jazz

# File: .package
```
(package jazz.sample

  (title "Sample")
  (description "Jazz samples")
  (authors "Guillaume Cartier")
  (stage sample)
  (root "src")
  (products (jazz.sample (dependencies jazz)))
  (project ".project"))
```
