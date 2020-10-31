---
title: Arrow lambda not supported in static function.
description: Angular build error
date: 2020-10-31
tags:
  - angular
  - build
  - error
layout: layouts/post.njk
---
Na verdade, isso é um erro do compilador Angular e não é um bug.

As funções lambda não são suportadas em métodos estáticos pelo compiler.

## Solution

Dito isso, não entre em pânico, há uma maneira de superar isso usando o sinalizador @dynamic que instruirá o compilador a não emitir um erro.

``` ts/1-2,5
/**
 * @dynamic
 */
export class FireAuthGuard {

  static allowOnly = (role: string) => hasCustomClaim(role)

}
```
