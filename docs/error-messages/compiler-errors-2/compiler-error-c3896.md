---
title: Derleyici Hatası C3896
ms.date: 11/04/2016
f1_keywords:
- C3896
helpviewer_keywords:
- C3896
ms.assetid: eb8be0f6-5b4e-4d71-8285-8a2a94f8ba29
ms.openlocfilehash: 00e103720dc666b17566b67da19d4e908bb3addd
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62385530"
---
# <a name="compiler-error-c3896"></a>Derleyici Hatası C3896

'member': hatalı Başlatıcı: Bu sabit değerli veri üyesi yalnızca 'nullptr' ile başlatılabilir

A [değişmez değer](../../extensions/literal-cpp-component-extensions.md) veri üyesi başlatılan yanlış.  Bkz: [nullptr](../../extensions/nullptr-cpp-component-extensions.md) daha fazla bilgi için.

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