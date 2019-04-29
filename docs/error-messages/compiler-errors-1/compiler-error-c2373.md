---
title: Derleyici Hatası C2373
ms.date: 11/04/2016
f1_keywords:
- C2373
helpviewer_keywords:
- C2373
ms.assetid: 7a08bf0b-852d-48be-ba75-70df9f4b5951
ms.openlocfilehash: 967bdec10e0e1c04083770d52da930837d8eeb7e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62339084"
---
# <a name="compiler-error-c2373"></a>Derleyici Hatası C2373

'identifier': yeniden tanımlama; tür değiştiricileri farklı

Tanımlayıcı ile farklı tür değiştiricisi zaten tanımlandı.

Aşağıdaki örnek, C2373 oluşturur:

```
// C2373.h
void __clrcall func( void );
const int i = 20;
```

ve ardından:

```
// C2373.cpp
// compile with: /c
#include "C2373.h"
extern void __cdecl func( void );   // C2373
extern void __clrcall func( void );   // OK

extern int i;   // C2373
extern const int i;   // OK
```