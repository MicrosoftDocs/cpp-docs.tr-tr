---
title: Derleyici Hatası C2877
ms.date: 11/04/2016
f1_keywords:
- C2877
helpviewer_keywords:
- C2877
ms.assetid: 0b54837e-fcae-4d90-9658-623250435e24
ms.openlocfilehash: 093efbf0c329967983c1808ee46011425745515f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62390639"
---
# <a name="compiler-error-c2877"></a>Derleyici Hatası C2877

'symbol', 'sınıfı' erişilebilir değil.

Bir temel sınıftan türetilmiş tüm üyeler türetilen sınıfta erişilebilir olmalıdır.

Aşağıdaki örnek, C2877 oluşturur:

```
// C2877.cpp
// compile with: /c
class A {
private:
   int a;
};

class B : public A {
   using A::a;   // C2877
};
```