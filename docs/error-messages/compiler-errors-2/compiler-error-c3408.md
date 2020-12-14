---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3408'
title: Derleyici hatası C3408
ms.date: 11/04/2016
f1_keywords:
- C3408
helpviewer_keywords:
- C3408
ms.assetid: 1f5ea979-fb1e-4214-b310-6fd6ca8249b1
ms.openlocfilehash: 32ec9b93e7025462e0faa021c455dc3a221d5447
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97313170"
---
# <a name="compiler-error-c3408"></a>Derleyici hatası C3408

' Attribute ': özniteliğe şablon tanımlarında izin verilmiyor

Öznitelikler şablon tanımlarına uygulanamaz.

## <a name="example"></a>Örnek

Aşağıdaki örnek C3408 oluşturur.

```cpp
// C3408.cpp
// compile with: /c
template <class T> struct PTS {
   enum {
      IsPointer = 0,
      IsPointerToDataMember = 0
   };
};

template <class T>
[coclass]   // C3408
struct PTS<T*> {
   enum {
      IsPointer = 1,
      IsPointerToDataMember = 0
   };
};

template
<class T, class U>
struct PTS<T U::*> {
   enum {
      IsPointer = 1,
      IsPointerToDataMember = 1
   };
};

struct S{};

extern "C" int printf(const char*,...);

int main() {
   S s, *pS;
   int S::*ptm;

   printf("PTS<S>::IsPointer == %d PTS<S>::IsPointerToDataMember == %d\n", PTS<S>::IsPointer, PTS<S>:: IsPointerToDataMember);
   printf("PTS<S*>::IsPointer == %d PTS<S*>::IsPointerToDataMember == %d\n", PTS<S*>::IsPointer, PTS<S*>:: IsPointerToDataMember);
   printf("PTS<int S::*>::IsPointer == %d PTS<int S::*>::IsPointerToDataMember == %d\n", PTS<int S::*>::IsPointer, PTS<int S::*>:: IsPointerToDataMember);
}
```
