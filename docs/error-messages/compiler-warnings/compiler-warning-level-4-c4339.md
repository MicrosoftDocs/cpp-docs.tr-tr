---
title: Derleyici Uyarısı (düzey 4) C4339 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4339
dev_langs:
- C++
helpviewer_keywords:
- C4339
ms.assetid: 5b83353d-7777-4afb-8476-3c368349028c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9ab96374beffed9822b20f4f10db812f170ea6cc
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46025236"
---
# <a name="compiler-warning-level-4-c4339"></a>Derleyici Uyarısı (düzey 4) C4339

'type': Tanımsız Tür algılandı WinRT veya CLR meta verilerinde - bu türün kullanılması çalışma zamanı özel durumuna neden

Windows çalışma zamanı veya ortak dil çalışma zamanı için derlenmiş kodda bir türü tanımlanmadı. Olası çalışma zamanı özel önlemek için türü tanımlar.

Varsayılan olarak bu uyarıyı kapalıdır. Bkz: [derleyici uyarıları emin olan kapalı varsayılan](../../preprocessor/compiler-warnings-that-are-off-by-default.md) daha fazla bilgi için.

Aşağıdaki örnek, C4339 oluşturur ve bu sorunun nasıl gösterir:

```
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