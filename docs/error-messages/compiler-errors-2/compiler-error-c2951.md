---
title: Derleyici hatası C2951
ms.date: 11/04/2016
f1_keywords:
- C2951
helpviewer_keywords:
- C2951
ms.assetid: c6f95aa2-c894-425b-a51c-d40d70c8daa1
ms.openlocfilehash: fdb837f8e9a9b769d470b70b962ce63d144161e1
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755986"
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
