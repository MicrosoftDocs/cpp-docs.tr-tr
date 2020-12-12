---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2939'
title: Derleyici hatası C2939
ms.date: 11/04/2016
f1_keywords:
- C2939
helpviewer_keywords:
- C2939
ms.assetid: 455b050b-f2dc-4b5b-bd6a-e1f81d3d1644
ms.openlocfilehash: 465d2d9535a1c8f393e21b4ef48707f8e5fab89b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97323031"
---
# <a name="compiler-error-c2939"></a>Derleyici hatası C2939

' class ': tür sınıfı kimliği yerel bir veri değişkeni olarak yeniden tanımlandı

Genel veya şablon sınıfını yerel veri değişkeni olarak kullanamazsınız.

Bu hata, küme ayraçları yanlış bir şekilde eşleştirildiği için oluşur.

Aşağıdaki örnek C2939 oluşturur:

```cpp
// C2939.cpp
template<class T>
struct TC { };
int main() {
   int TC<int>;   // C2939
   int TC;   // OK
}
```

C2939, genel türler kullanılırken de oluşabilir:

```cpp
// C2939b.cpp
// compile with: /clr
generic<class T>
ref struct GC { };

int main() {
   int GC<int>;   // C2939
   int GC;   // OK
}
```
