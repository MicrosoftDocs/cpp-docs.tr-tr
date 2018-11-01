---
title: Derleyici Hatası C3266
ms.date: 11/04/2016
f1_keywords:
- C3266
helpviewer_keywords:
- C3266
ms.assetid: 7375c099-acb7-42f6-898d-57cfefa010b8
ms.openlocfilehash: d93056116ebf2f4646dc34f848b073fe6401b9db
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50475175"
---
# <a name="compiler-error-c3266"></a>Derleyici Hatası C3266

'class': sınıf oluşturucusu bir 'void' parametre listesine sahip olmalıdır

/ CLR programlama kullanarak bir sınıf içinde sınıf oluşturucuları parametreleri alamıyor.

Aşağıdaki örnek, C3266 oluşturur:

```
// C3266.cpp
// compile with: /clr

ref class X {
   static X(int i) { // C3266
   // try the following line instead
   // static X() {
   }
};

int main() {
}
```
