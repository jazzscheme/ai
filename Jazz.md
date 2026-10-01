# Jazz guidelines

Prefer functional programming when state doesn't need to be changed and only use classes when needed

## Gambit

Jazz is built on top of Gambit Scheme and can use all of Gambit's primitives

Gambit (declare) is baked into the jazz language and not needed

## Comments

Do not add comments to code. The core design philosophy is that the code should be so clear as to be clearer than any documentation

Section ;;;; comments are fine

A module overview comment at the top is also fine

## Method Invocation and Field Access (No Dot-Notation)

JazzScheme strictly adheres to prefix Lisp syntax for all operations. There is **absolute zero dot-notation** (`object.method` or `object.field`) in the language. 

* **Method Invocations Outside Class Boundaries:** To call a method on an instance, it is executed as a standard prefix procedure where the method name leads, followed by the target object instance and any arguments.
  * *Incorrect:* `(stream.write data)` or `stream.write(data)`
  * *Correct:* `(write-string data stream)` or `(write stream data)` depending on the interface.
  * *Generic Form:* `(method-name instance-symbol arg1 arg2)`

* **Slot Access:** Slot values are retrieved and assigned via standard functional procedures or macros, not structural member-access tokens.

## Native Collections and Key-Value Associations (No Dictionary)

There is **no native class or structure named `Dictionary`** in JazzScheme. Do not instantiate `(new Dictionary)`. 

* **Association Lists (Alists):** For basic, functional key-value mappings where state changes are minimized, prefer standard Lisp association lists (`'((key1 . val1) (key2 . val2))`). Manipulate them using classic functional primitives like `assoc`, `aconso`, or standard pair accessors.
* **Hash Tables:** When high-performance lookups are structurally necessary, use the native Scheme hash table API rather than generic class types.
* **Anti-Pattern Refusal:** Never guess lookup method signatures like `metadata.get` or `set-dictionary-value!`. Every collection access must use strict prefix functional syntax.
