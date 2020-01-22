---
title: Derleyici hatası C2346
ms.date: 11/04/2016
f1_keywords:
- C2346
helpviewer_keywords:
- C2346
ms.assetid: 246145be-5645-4cd6-867c-e3bc39e33dca
ms.openlocfilehash: 91f2bac38166a8972193a7aaa7e84913b941c799
ms.sourcegitcommit: a930a9b47bd95599265d6ba83bb87e46ae748949
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/22/2020
ms.locfileid: "76518328"
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

int main()
{
   S s;
}
```
