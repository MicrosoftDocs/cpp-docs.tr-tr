---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2165'
title: Derleyici hatası C2165
ms.date: 11/04/2016
f1_keywords:
- C2165
helpviewer_keywords:
- C2165
ms.assetid: b108313b-b8cb-4dce-b2ec-f2b31c9cdc87
ms.openlocfilehash: 6c019a1f2fe9edd92d1ebd57b67fd65da262accf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97274638"
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
