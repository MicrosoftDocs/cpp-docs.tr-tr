---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2976'
title: Derleyici hatası C2976
ms.date: 11/04/2016
f1_keywords:
- C2976
helpviewer_keywords:
- C2976
ms.assetid: d9bf9836-325e-4f72-a7e3-a67cf19d32e7
ms.openlocfilehash: 645b4437bba022e53d018aec18d81b5f108d4d93
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97281905"
---
# <a name="compiler-error-c2976"></a>Derleyici hatası C2976

' tanımlayıcı ': çok az sayıda bağımsız değişken

Genel veya şablonda bir veya daha fazla gerçek bağımsız değişken eksik. Doğru parametre sayısını bulmak için genel veya şablon bildirimini denetleyin.

Bu hata, C++ standart kitaplığı bileşenlerinde eksik şablon bağımsız değişkenlerinin oluşmasına neden olabilir.

Aşağıdaki örnek C2976 oluşturur:

```cpp
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

C2976, genel türler kullanılırken de oluşabilir:

```cpp
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
