---
title: Derleyici Uyarısı C4956
ms.date: 11/04/2016
f1_keywords:
- C4956
helpviewer_keywords:
- C4956
ms.assetid: 9154f2d1-d49f-4e07-90d2-0e9bc028011a
ms.openlocfilehash: 474bdfa6eb670f39a2876b0c1490e7254cf216e7
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80164915"
---
# <a name="compiler-warning-c4956"></a>Derleyici Uyarısı C4956

> '*Type*': Bu tür doğrulanabilir değil

## <a name="remarks"></a>Açıklamalar

[/Clr: Safe](../../build/reference/clr-common-language-runtime-compilation.md) belirtildiğinde ve kodunuz doğrulanabilir olmayan bir tür içerdiğinde bu uyarı oluşturulur. **/Clr: Safe** derleyici seçeneği visual Studio 2015 ' de kullanımdan kaldırılmıştır ve visual Studio 2017 ' de desteklenmez.

Daha fazla bilgi için bkz. [saf ve Doğrulanabilen kodC++(/CLI)](../../dotnet/pure-and-verifiable-code-cpp-cli.md).

Bu uyarı bir hata olarak verilir ve [Uyarı](../../preprocessor/warning.md) pragması veya [/WD](../../build/reference/compiler-option-warning-level.md) derleyici seçeneği ile devre dışı bırakılabilir.

## <a name="example"></a>Örnek

Aşağıdaki örnek C4956 oluşturur:

```cpp
// C4956.cpp
// compile with: /clr:safe
int* p;   // C4956
```
