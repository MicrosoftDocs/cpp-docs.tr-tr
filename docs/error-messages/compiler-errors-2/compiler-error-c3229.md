---
title: Derleyici Hatası C3229
ms.date: 11/04/2016
f1_keywords:
- C3229
helpviewer_keywords:
- C3229
ms.assetid: f2d90923-aa8b-444f-ab10-1f37dbb864e1
ms.openlocfilehash: a3716bafd92bbcd5875ab2ba317f0c6826289c59
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50543890"
---
# <a name="compiler-error-c3229"></a>Derleyici Hatası C3229

'type': genel tür parametresi yöneltmelere izin verilmez

Genel parametreler ile kullanamazsınız `*`, `^`, veya `&`.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3229 oluşturur.

```
// C3229.cpp
// compile with: /clr /c
generic <class T>
ref class C {
   T^ t;   // C3229
};

// OK
generic <class T>
ref class D {
   T u;
};
```

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3229 oluşturur.

```
// C3229_b.cpp
// compile with: /clr /c
generic <class T>   // OK
ref class Utils {
   static void sort(T elems[], size_t size);   // C3229
   static void sort2(T elems, size_t size);   // OK
};
```