---
title: Derleyici Uyarısı (düzey 2) C4356
ms.date: 11/04/2016
f1_keywords:
- C4356
helpviewer_keywords:
- C4356
ms.assetid: 3af3defe-de33-43b6-bd6c-2c2e09e34f3f
ms.openlocfilehash: ffcf0098799b893f83e331b3b4cc602e1b538b1c
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80161834"
---
# <a name="compiler-warning-level-2-c4356"></a>Derleyici Uyarısı (düzey 2) C4356

' üye ': statik veri üyesi türetilmiş sınıf aracılığıyla başlatılamaz

Statik veri üyesinin başlatılması hatalı biçimlendirilmiş. Derleyici başlatmayı kabul etti. Uyarıyı önlemek için, üyeyi temel sınıf aracılığıyla başlatın.

Bu uyarıyı gizlemek için [Uyarı](../../preprocessor/warning.md) pragmasını kullanın.

Aşağıdaki örnek C4356 oluşturur:

```cpp
// C4356.cpp
// compile with: /W2 /EHsc
#include <iostream>

template <class T>
class C {
   static int n;
};

class D : C<int> {};

int D::n = 0; // C4356
// try the following line instead
// int C<int>::n = 0;

class A {
public:
   static int n;
};

class B : public A {};

int B::n = 10;   // C4356
// try the following line instead
// int A::n = 99;

int main() {
   using namespace std;
   cout << B::n << endl;
}
```
