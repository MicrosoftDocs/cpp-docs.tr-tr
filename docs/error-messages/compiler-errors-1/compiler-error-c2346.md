---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2346'
title: Derleyici hatası C2346
ms.date: 11/04/2016
f1_keywords:
- C2346
helpviewer_keywords:
- C2346
ms.assetid: 246145be-5645-4cd6-867c-e3bc39e33dca
ms.openlocfilehash: eb2bbda6c7f7e0c9213b35a794b915967d03321f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97298376"
---
# <a name="compiler-error-c2346"></a>Derleyici hatası C2346

' function ' yerel olarak derlenemiyor: neden

Derleyici MSIL 'ye bir işlev derleyemiyor.

Daha fazla bilgi için bkz. [yönetilen, yönetilmeyen](../../preprocessor/managed-unmanaged.md) ve [/clr (ortak dil çalışma zamanı derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md).

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

1. İşlevde MSIL 'e Derlenemeyen kodu kaldırın.

1. Modülü **/clr** ile derleme veya yönetilmeyen pragma ile yönetilmeyen olarak işaretleme.

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
