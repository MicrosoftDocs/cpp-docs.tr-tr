---
title: Derleyici Hatası C2346 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2346
dev_langs:
- C++
helpviewer_keywords:
- C2346
ms.assetid: 246145be-5645-4cd6-867c-e3bc39e33dca
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5ec916bcdce1a43c597d8cfae10e5393cbeb99ee
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46108620"
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