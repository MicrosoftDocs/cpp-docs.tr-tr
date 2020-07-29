---
title: Derleyici hatası C2883
ms.date: 11/04/2016
f1_keywords:
- C2883
helpviewer_keywords:
- C2883
ms.assetid: 5c6d689d-ed42-41ad-b5c0-e9c2e0b8c356
ms.openlocfilehash: fcd97a2f362e50ec856e53da2603c29e07595670
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87233476"
---
# <a name="compiler-error-c2883"></a>Derleyici hatası C2883

' name ': işlev bildirimi, bildirim kullanılarak tanıtılan ' Identifier ' ile çakışıyor

Bir işlevi birden çok kez tanımlamaya çalıştınız. İlk tanım, bildirimi olan bir ad alanından yapıldı **`using`** . İkincisi yerel bir tanımdır.

Aşağıdaki örnek C2883 oluşturur:

```cpp
// C2883.cpp
namespace A {
   void z(int);
}

int main() {
   using A::z;
   void z(int);   // C2883  z is already defined
}
```
