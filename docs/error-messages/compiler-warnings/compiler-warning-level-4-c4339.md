---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 4) C4339'
title: Derleyici Uyarısı (düzey 4) C4339
ms.date: 11/04/2016
f1_keywords:
- C4339
helpviewer_keywords:
- C4339
ms.assetid: 5b83353d-7777-4afb-8476-3c368349028c
ms.openlocfilehash: e05a7a73ac0cbbf056e5e30db0989e7fe933d01e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97294528"
---
# <a name="compiler-warning-level-4-c4339"></a>Derleyici Uyarısı (düzey 4) C4339

' Type ': WinRT veya CLR meta verilerinde tanımsız tür kullanımı algılandı-Bu türün kullanılması çalışma zamanı özel durumuna neden olabilir

Windows Çalışma Zamanı veya ortak dil çalışma zamanı için derlenen kodda bir tür tanımlanmadı. Olası bir çalışma zamanı özel durumunu önlemek için türü tanımlayın.

Bu uyarı varsayılan olarak kapalıdır. Daha fazla bilgi için bkz. [Varsayılan olarak kapalı olan Derleyici uyarıları](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .

Aşağıdaki örnek C4339 oluşturur ve nasıl düzeltileceğini gösterir:

```cpp
// C4339.cpp
// compile with: /W4 /clr /c
// C4339 expected
#pragma warning(default : 4339)

// Delete the following line to resolve.
class A;

// Uncomment the following line to resolve.
// class A{};

class X {
public:
   X() {}

   virtual A *mf() {
      return 0;
   }
};

X * f() {
   return new X();
}
```
