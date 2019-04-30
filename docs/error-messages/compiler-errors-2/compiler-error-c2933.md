---
title: Derleyici Hatası C2933
ms.date: 11/04/2016
f1_keywords:
- C2933
helpviewer_keywords:
- C2933
ms.assetid: 394891e3-6b52-4b61-83d2-a1c5125d9bd5
ms.openlocfilehash: 8764ce7f79243eec931904378522b90a41b633a7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62385907"
---
# <a name="compiler-error-c2933"></a>Derleyici Hatası C2933

'class': tür-sınıf-id 'identifier' tür tanımı üyesi olarak yeniden tanımlandı

Bir genel veya Şablon sınıfı olarak kullanılamaz bir `typedef` üyesi.

Aşağıdaki örnek, C2933 oluşturur:

```
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

C2933, genel türler kullanırken da meydana gelebilir:

```
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