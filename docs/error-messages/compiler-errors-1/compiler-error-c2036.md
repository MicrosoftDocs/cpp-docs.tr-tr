---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2036'
title: Derleyici hatası C2036
ms.date: 11/04/2016
f1_keywords:
- C2036
helpviewer_keywords:
- C2036
ms.assetid: 895821a9-65d1-44b5-bde1-dae827f3e486
ms.openlocfilehash: 53e036ea1bf27fd9502a3c21353b450962bc0db9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97175397"
---
# <a name="compiler-error-c2036"></a>Derleyici hatası C2036

' tanımlayıcı ': Bilinmeyen boyut

Üzerinde bir işlem, `identifier` belirlenemediği veri nesnesinin boyutunu gerektirir.

## <a name="examples"></a>Örnekler

Aşağıdaki örnek C2036 oluşturur.

```c
// C2036.c
// a C program
struct A* pA;
struct B { int i; } *pB;
int main() {
   pA++;   // C2036, size of A not known
   ((char*)pA)++;   // OK

   pB++;   // OK
}
```

Aşağıdaki örnek C2036 oluşturur.

```cpp
// C2036_2.cpp
// a C++ program
struct A* pA;
int main() {
   pA++;   // C2036, size of A not known
   ((char*&)pA)++;   // OK, if sizeof(A) == sizeof(char)
}
```
