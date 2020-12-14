---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2933'
title: Derleyici hatası C2933
ms.date: 11/04/2016
f1_keywords:
- C2933
helpviewer_keywords:
- C2933
ms.assetid: 394891e3-6b52-4b61-83d2-a1c5125d9bd5
ms.openlocfilehash: be815b24b892cc1ef835654df81c7d47483f3730
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97297427"
---
# <a name="compiler-error-c2933"></a>Derleyici hatası C2933

' class ': tür sınıfı kimliği, ' Identifier ' öğesinin typedef üyesi olarak yeniden tanımlandı

Genel veya şablon sınıfını üye olarak kullanamazsınız **`typedef`** .

Aşağıdaki örnek C2933 oluşturur:

```cpp
// C2933.cpp
// compile with: /c
template<class T> struct TC { };
struct MyStruct {
   typedef int TC<int>;   // C2933
};

struct TC2 { };
struct MyStruct2 {
   typedef int TC2;
};
```

C2933, genel türler kullanılırken de oluşabilir:

```cpp
// C2933b.cpp
// compile with: /clr /c
generic<class T> ref struct GC { };
struct MyStruct {
   typedef int GC<int>;   // C2933
};

ref struct GC2 { };
struct MyStruct2 {
   typedef int GC2;
};
```
