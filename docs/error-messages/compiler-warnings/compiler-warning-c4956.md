---
title: Derleyici Uyarısı C4956
ms.date: 11/04/2016
f1_keywords:
- C4956
helpviewer_keywords:
- C4956
ms.assetid: 9154f2d1-d49f-4e07-90d2-0e9bc028011a
ms.openlocfilehash: c15de8b22f56a2555cc763a45153139b1df01a31
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62280848"
---
# <a name="compiler-warning-c4956"></a>Derleyici Uyarısı C4956

> '*türü*': Bu tür doğrulanabilir değil

## <a name="remarks"></a>Açıklamalar

Bu uyarı oluşturulur, [/CLR: safe](../../build/reference/clr-common-language-runtime-compilation.md) belirtilir ve doğrulanabilir değil bir tür kod içerir. **/CLR: safe** derleyici seçeneğini Visual Studio 2015'te kullanım dışı ve Visual Studio 2017'de desteklenmiyor.

Daha fazla bilgi için [saf ve doğrulanabilen kod (C++/CLI)](../../dotnet/pure-and-verifiable-code-cpp-cli.md).

Bu uyarı hata olarak verilir ve ile devre dışı bırakılabilir [uyarı](../../preprocessor/warning.md) pragma veya [/wd](../../build/reference/compiler-option-warning-level.md) derleyici seçeneği.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4956 oluşturur:

```cpp
// C4956.cpp
// compile with: /clr:safe
int* p;   // C4956
```