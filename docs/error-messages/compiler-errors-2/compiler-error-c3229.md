---
title: Derleyici hatası C3229
ms.date: 11/04/2016
f1_keywords:
- C3229
helpviewer_keywords:
- C3229
ms.assetid: f2d90923-aa8b-444f-ab10-1f37dbb864e1
ms.openlocfilehash: bf205259eda45c79ac0c3c772d4f437cb3ac14b8
ms.sourcegitcommit: 72161bcd21d1ad9cc3f12261aa84a5b026884afa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2020
ms.locfileid: "90743093"
---
# <a name="compiler-error-c3229"></a>Derleyici hatası C3229

' Type ': genel tür parametresinde yöneltmelere izin verilmiyor

, Veya ile genel parametreleri kullanamazsınız `*` `^` `&` .

## <a name="examples"></a>Örnekler

Aşağıdaki örnek C3229 oluşturur.

```cpp
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

Aşağıdaki örnek C3229 oluşturur.

```cpp
// C3229_b.cpp
// compile with: /clr /c
generic <class T>   // OK
ref class Utils {
   static void sort(T elems[], size_t size);   // C3229
   static void sort2(T elems, size_t size);   // OK
};
```
