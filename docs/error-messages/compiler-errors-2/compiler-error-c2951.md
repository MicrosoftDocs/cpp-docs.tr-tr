---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2951'
title: Derleyici hatası C2951
ms.date: 11/04/2016
f1_keywords:
- C2951
helpviewer_keywords:
- C2951
ms.assetid: c6f95aa2-c894-425b-a51c-d40d70c8daa1
ms.openlocfilehash: 7f3030764cdd36d40fbd78a8c3768c7dc1085c21
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97322113"
---
# <a name="compiler-error-c2951"></a>Derleyici hatası C2951

tür bildirimlerine yalnızca genel, ad alanı veya sınıf kapsamında izin verilir

Genel veya ad alanı kapsamı dışında genel veya şablon sınıfı bildiremezsiniz. Genel veya şablon bildirimlerinizi bir içerme dosyasında yaparsanız, içerme dosyasının genel kapsamda olduğundan emin olun.

Aşağıdaki örnek C2951 oluşturur:

```cpp
// C2951.cpp
template <class T>
class A {};

int main() {
   template <class T>   // C2951
   class B {};
}
```

C2951, genel türler kullanılırken de oluşabilir:

```cpp
// C2951b.cpp
// compile with: /clr /c

// OK
generic <class T>
ref class GC { };

int main() {
   generic <class T> ref class GC2 {};   // C2951
}
```
