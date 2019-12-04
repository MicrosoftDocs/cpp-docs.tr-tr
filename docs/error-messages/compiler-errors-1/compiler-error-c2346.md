---
title: Derleyici hatası C2346
ms.date: 11/04/2016
f1_keywords:
- C2346
helpviewer_keywords:
- C2346
ms.assetid: 246145be-5645-4cd6-867c-e3bc39e33dca
ms.openlocfilehash: fc2aeac02ecc3f29406c2288051ca6cd9d3a4923
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74760016"
---
# <a name="compiler-error-c2346"></a>Derleyici hatası C2346

' function ' yerel olarak derlenemiyor: neden

Derleyici MSIL 'ye bir işlev derleyemiyor.

Daha fazla bilgi için bkz. [yönetilen, yönetilmeyen](../../preprocessor/managed-unmanaged.md) ve [/clr (ortak dil çalışma zamanı derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md).

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

1. İşlevde MSIL 'e Derlenemeyen kodu kaldırın.

1. Modülü **/clr**ile derleme veya yönetilmeyen pragma ile yönetilmeyen olarak işaretleme.

## <a name="example"></a>Örnek

Aşağıdaki örnek C2346 oluşturur.

```cpp
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
