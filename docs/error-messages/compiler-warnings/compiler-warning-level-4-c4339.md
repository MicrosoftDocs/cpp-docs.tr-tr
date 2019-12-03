---
title: Derleyici Uyarısı (düzey 4) C4339
ms.date: 11/04/2016
f1_keywords:
- C4339
helpviewer_keywords:
- C4339
ms.assetid: 5b83353d-7777-4afb-8476-3c368349028c
ms.openlocfilehash: fffdaa255f6b8f2259488df610f163bebf8d6dec
ms.sourcegitcommit: d0504e2337bb671e78ec6dd1c7b05d89e7adf6a7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/02/2019
ms.locfileid: "74683288"
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