---
title: Derleyici Hatası C2923
ms.date: 11/04/2016
f1_keywords:
- C2923
helpviewer_keywords:
- C2923
ms.assetid: 6b92933b-13ef-4124-99d9-b89f9fdae030
ms.openlocfilehash: 885a3a09d43d8c3c479d11e22342487d1a1958d4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50593628"
---
# <a name="compiler-error-c2923"></a>Derleyici Hatası C2923

'type': 'identifier' parametresi 'param' için geçerli bir şablon türü bağımsız değişkeni değil

Genel ve şablon örneği oluşturmak için gereken bir tür bağımsız değişken listesi eksik. Şablon veya genel bildirimi denetleyin.

Aşağıdaki örnek, C2923 oluşturur:

```
// C2923.cpp
template <class T> struct TC {};
int x;
int main() {
   TC<x>* tc2;   // C2923
   TC<int>* tc2;   // OK
}
```

C2923, genel türler kullanırken da meydana gelebilir:

```
// C2923b.cpp
// compile with: /clr /c
generic <class T> ref struct GC {};

int x;

int main() {
   GC<x>^ gc2;   // C2923
   GC<int>^ gc2;   // OK
}
```