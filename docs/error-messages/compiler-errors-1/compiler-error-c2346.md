---
title: Derleyici Hatası C2346
ms.date: 11/04/2016
f1_keywords:
- C2346
helpviewer_keywords:
- C2346
ms.assetid: 246145be-5645-4cd6-867c-e3bc39e33dca
ms.openlocfilehash: a6d75ca671e22203cb40ca18de21606834eeefa8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50527367"
---
# <a name="compiler-error-c2346"></a>Derleyici Hatası C2346

'function' derlenemez yerel olarak: nedeni

Derleyici bir işleve MSIL derleyemiyor.

Daha fazla bilgi için [yönetilen, yönetilmeyen](../../preprocessor/managed-unmanaged.md) ve [/CLR (ortak dil çalışma zamanı derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md).

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

1. İşlevinde, MSIL olarak derlenmiş kod kaldırın.

1. Ya da modülüyle derlenmiyor **/CLR**, veya işlev yönetilmeyen pragma ile yönetilmeyen olarak işaretleyin.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C2346 oluşturur.

```
// C2346.cpp
// processor: x86
// compile with: /clr
// C2346 expected
struct S
{
   S()
   {
      { __asm { nop } }
   }
   virtual __clrcall ~S() { }
};

void main()
{
   S s;
}
```