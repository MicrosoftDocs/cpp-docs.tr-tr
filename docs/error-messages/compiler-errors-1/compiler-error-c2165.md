---
title: Derleyici hatası C2165
ms.date: 11/04/2016
f1_keywords:
- C2165
helpviewer_keywords:
- C2165
ms.assetid: b108313b-b8cb-4dce-b2ec-f2b31c9cdc87
ms.openlocfilehash: 29637dd9cb2b1faab537a970df9ef3d76fc26e0c
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87216355"
---
# <a name="compiler-error-c2165"></a>Derleyici hatası C2165

' anahtar sözcüğü ': veri işaretçileri değiştirilemez

**`__stdcall`**, **`__cdecl`** Veya **`__fastcall`** anahtar sözcüğü, bir işaretçiyi veri işaretçisi üzerinde değiştirmeye çalışır.

Aşağıdaki örnek C2165 oluşturur:

```cpp
// C2165.cpp
// compile with: /c
char __cdecl *p;   // C2165
char *p;   // OK
```
