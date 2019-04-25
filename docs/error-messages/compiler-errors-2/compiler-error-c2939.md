---
title: Derleyici Hatası C2939
ms.date: 11/04/2016
f1_keywords:
- C2939
helpviewer_keywords:
- C2939
ms.assetid: 455b050b-f2dc-4b5b-bd6a-e1f81d3d1644
ms.openlocfilehash: 59b2f63ba12a644f13b3586fbf6eec4d5bfa8be5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62302663"
---
# <a name="compiler-error-c2939"></a>Derleyici Hatası C2939

'class': türü sınıf kimliği bir yerel veri değişken olarak yeniden tanımlandı

Yerel veri değişkeni olarak bir genel veya Şablon sınıfı kullanamazsınız.

Küme ayraçları yanlış eşleşirse bu hataya neden olabilir.

Aşağıdaki örnek, C2939 oluşturur:

```
// C2939.cpp
template<class T>
struct TC { };
int main() {
   int TC<int>;   // C2939
   int TC;   // OK
}
```

C2939, genel türler kullanırken da meydana gelebilir:

```
// C2939b.cpp
// compile with: /clr
generic<class T>
ref struct GC { };

int main() {
   int GC<int>;   // C2939
   int GC;   // OK
}
```