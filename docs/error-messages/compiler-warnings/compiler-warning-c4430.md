---
title: Derleyici Uyarısı C4430
ms.date: 11/04/2016
f1_keywords:
- C4430
helpviewer_keywords:
- C4430
ms.assetid: 12efbfff-aa58-4a86-a7d6-2c6a12d01dd3
ms.openlocfilehash: 091d988a5af277e78a2954eb5b0b95bc64c56069
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80165268"
---
# <a name="compiler-warning-c4430"></a>Derleyici Uyarısı C4430

tür belirticisi eksik - int varsayıldı. Not: C++ varsayılan int 'i desteklemez

Bu hata, Visual Studio 2005 için yapılan derleyici uygunluk işinin bir sonucu olarak oluşturulabilir: tüm bildirimlerin türü açıkça belirtmesi gerekir; int artık kabul değildir.

C4430 her zaman bir hata olarak verilir.  Bu uyarıyı `#pragma warning` veya **/WD**; ile devre dışı bırakabilirsiniz. daha fazla bilgi için bkz. [Warning](../../preprocessor/warning.md) [;/W,/W0,/W1,/W2,/W3,/W4,/W1,/W2,/W3,/W4,/duvar,/WD,/we,/Wo,/WV,/WX (uyarı düzeyi)](../../build/reference/compiler-option-warning-level.md) .

## <a name="example"></a>Örnek

Aşağıdaki örnek C4430 oluşturur.

```cpp
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
