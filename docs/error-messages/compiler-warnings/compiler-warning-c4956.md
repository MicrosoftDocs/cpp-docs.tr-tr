---
description: 'Hakkında daha fazla bilgi edinin: derleyici uyarısı C4956'
title: Derleyici Uyarısı C4956
ms.date: 11/04/2016
f1_keywords:
- C4956
helpviewer_keywords:
- C4956
ms.assetid: 9154f2d1-d49f-4e07-90d2-0e9bc028011a
ms.openlocfilehash: 4a92c6329bf4cdd764fd7f419d8011d4dfde0202
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97314847"
---
# <a name="compiler-warning-c4956"></a>Derleyici Uyarısı C4956

> '*Type*': Bu tür doğrulanabilir değil

## <a name="remarks"></a>Açıklamalar

[/Clr: Safe](../../build/reference/clr-common-language-runtime-compilation.md) belirtildiğinde ve kodunuz doğrulanabilir olmayan bir tür içerdiğinde bu uyarı oluşturulur. **/Clr: Safe** derleyici seçeneği visual Studio 2015 ' de kullanımdan kaldırılmıştır ve visual Studio 2017 ' de desteklenmez.

Daha fazla bilgi için bkz. [saf ve Doğrulanabilen kod (C++/CLI)](../../dotnet/pure-and-verifiable-code-cpp-cli.md).

Bu uyarı bir hata olarak verilir ve [Uyarı](../../preprocessor/warning.md) pragması veya [/WD](../../build/reference/compiler-option-warning-level.md) derleyici seçeneği ile devre dışı bırakılabilir.

## <a name="example"></a>Örnek

Aşağıdaki örnek C4956 oluşturur:

```cpp
// C4956.cpp
// compile with: /clr:safe
int* p;   // C4956
```
