---
title: Derleyici Hatası C2012
ms.date: 11/04/2016
f1_keywords:
- C2012
helpviewer_keywords:
- C2012
ms.assetid: 9f0d8162-c0b3-4234-a41f-836fdb75c84e
ms.openlocfilehash: 85c3ad1d127dcabeeed0c5727ba6bbbca86f7898
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62364473"
---
# <a name="compiler-error-c2012"></a>Derleyici Hatası C2012

işaretinden sonra ad eksik ' <'

Bir `#include` yönergesi gerekli dosya adı eksik.

Aşağıdaki örnek, C2012 oluşturur:

```
// C2012.cpp
#include <   // C2012 include the filename to resolve
```

Olası çözüm:

```
// C2012b.cpp
// compile with: /c
#include <stdio.h>
```