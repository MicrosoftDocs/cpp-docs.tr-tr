---
title: Derleyici Uyarısı C4430
ms.date: 11/04/2016
f1_keywords:
- C4430
helpviewer_keywords:
- C4430
ms.assetid: 12efbfff-aa58-4a86-a7d6-2c6a12d01dd3
ms.openlocfilehash: 1d58efd57433a065f08e4111302f358405e3b9ab
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50639874"
---
# <a name="compiler-warning-c4430"></a>Derleyici Uyarısı C4430

tür belirticisi eksik - int varsayıldı. Not: C++ varsayılan int desteklemez

Bu hata için Visual C++ 2005 yapıldığı derleyici uyumluluğu iş sonucu olarak oluşturulan: tüm bildirimleri; türünü açıkça belirtmeniz gerekir artık int varsayıldı.

C4430 her zaman hata olarak verilir.  Bu uyarı ile kapatabilirsiniz `#pragma warning` veya **/wd**; bkz [uyarı](../../preprocessor/warning.md) veya [/w, /W0, / W1, / w2, / W3, / W4, / W1, / w2, / W3, / W4, /Wall, WD, / we Wo, wv, /WX (uyarı düzeyi)](../../build/reference/compiler-option-warning-level.md)daha fazla bilgi için.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4430 oluşturur.

```
// C4430.cpp
// compile with: /c
struct CMyClass {
   CUndeclared m_myClass;  // C4430
   int m_myClass;  // OK
};

typedef struct {
   POINT();   // C4430
   // try the following line instead
   // int POINT();
   unsigned x;
   unsigned y;
} POINT;
```