---
title: Derleyici Hatası C3896
ms.date: 11/04/2016
f1_keywords:
- C3896
helpviewer_keywords:
- C3896
ms.assetid: eb8be0f6-5b4e-4d71-8285-8a2a94f8ba29
ms.openlocfilehash: 32aed1dfd957035cdd60fa97bd9ec534de03cb06
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50547966"
---
# <a name="compiler-error-c3896"></a>Derleyici Hatası C3896

'member': hatalı Başlatıcı: Bu sabit değerli veri üyesi yalnızca 'nullptr' ile başlatılabilir

A [değişmez değer](../../windows/literal-cpp-component-extensions.md) veri üyesi başlatılan yanlış.  Bkz: [nullptr](../../windows/nullptr-cpp-component-extensions.md) daha fazla bilgi için.

Aşağıdaki örnek, C3896 oluşturur:

```
// C3896.cpp
// compile with: /clr /c
ref class R{};

value class V {
   literal R ^ r = "test";   // C3896
   literal R ^ r2 = nullptr;   // OK
};
```