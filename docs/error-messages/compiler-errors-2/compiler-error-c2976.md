---
title: Derleyici Hatası C2976
ms.date: 11/04/2016
f1_keywords:
- C2976
helpviewer_keywords:
- C2976
ms.assetid: d9bf9836-325e-4f72-a7e3-a67cf19d32e7
ms.openlocfilehash: 02771d7419c58ee4f0b6d7db46ba91fde253d9a9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50428505"
---
# <a name="compiler-error-c2976"></a>Derleyici Hatası C2976

'identifier': çok az tür bağımsız değişkeni

Genel veya şablon bir veya daha fazla gerçek bağımsız değişkenler eksik. Doğru parametreleri sayısını bulmak için genel veya şablon bildirimi denetleyin.

Bu hata, C++ Standart Kitaplığı bileşenlerinde şablon bağımsız değişkenleri eksik tarafından kaynaklanabilir.

Aşağıdaki örnek, C2976 oluşturur:

```
// C2976.cpp
template <class T>
struct TC {
   T t;
};
int main() {
   TC<>* t;   // C2976
   TC<int>* t2;   // OK
}
```

C2976, genel türler kullanırken da meydana gelebilir:

```
// C2976b.cpp
// compile with: /clr
generic <class T>
ref struct GC {
   T t;
};

int main() {
   GC<>^ g;   // C2976
   GC<int>^ g2;   // OK
}
```