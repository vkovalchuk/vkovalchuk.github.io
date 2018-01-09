---
title: 'Null, Null objects and Optional'
date: 2018-01-09 12:28:36
tags:
 - Java
 - Golang
 - FP
 - rant
---
There is constant tune "introducing NULL was a billion-dollar mistake!" and suggestions that mere eliminating NULL concept will solve this particular class of problems. Naive souls pushed through introduction of Optional into Java, like Maybe monad or Scala Option. So instead of checking for NULL you either call a map()/flatMap() or check for isPresent(). OK you never get NPE; instead you get a program that has no effect because the data are absent. A user liberated from seeing horrrors of HPE will log into account and see her list of credit cards empty. Much better now! Not being liberated from the money I mean.

Contrary to popular belief a NULL is not pure invention of computer geeks. It reflects part of business domain where some fact is not yet known, as in SQL. If there is no correct  value, developer will use something bogus which is equivalent for NULL, called NULL object. Union type helps by compiler warning that "here you must handle other possible type"; but then usual Java could be improved by compiler's nullability analysis and warnings. Though I must admit "Type! name" is shorter notation than "@NonNull Type name".

Go lang provided interesting solution where nil slice has length. It is safe to iterate so NPE for the nil goes away. I was surprized to see people arguing against "strange nil is an error". No, it's your impression that nil a C's NULL and causes memory fault is an error. Useful zero is exactly what NULL must be, and panic is the correct behavior for the call.