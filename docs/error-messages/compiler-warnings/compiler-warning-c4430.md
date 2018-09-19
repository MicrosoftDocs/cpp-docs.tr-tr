---
title: Derleyici Uyarısı C4430 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4430
dev_langs:
- C++
helpviewer_keywords:
- C4430
ms.assetid: 12efbfff-aa58-4a86-a7d6-2c6a12d01dd3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 79c0045b568a24ad6702e748e82a8ebd88c41044
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46093928"
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