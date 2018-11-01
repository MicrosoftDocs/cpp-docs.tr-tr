---
title: Derleyici Hatası C3389
ms.date: 11/04/2016
f1_keywords:
- C3389
helpviewer_keywords:
- C3389
ms.assetid: eaaffe17-23f2-413c-b1ad-f7220cfa1334
ms.openlocfilehash: 6a9568f3c3be88438eae1f28e12dc780301ead0b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50584307"
---
# <a name="compiler-error-c3389"></a>Derleyici Hatası C3389

> __declspec (*anahtar sözcüğü*) / CLR ile birlikte kullanılamaz: pure veya/CLR: safe

## <a name="remarks"></a>Açıklamalar

**/CLR: pure** ve **/CLR: safe** derleyici seçenekleri Visual Studio 2015'te kullanım dışı ve Visual Studio 2017'de desteklenmiyor.

A [__declspec](../../cpp/declspec.md) kullanılan değiştiricisi anlamına gelir. bir işlem durumu başına.  [/ CLR: pure](../../build/reference/clr-common-language-runtime-compilation.md) gelir bir başına [appdomain](../../cpp/appdomain.md) durumu.  Bu nedenle, bir değişken bildirme `keyword` **__declspec** değiştiricisi ve ile derleme **/CLR: pure** izin verilmiyor.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3389 oluşturur:

```cpp
// C3389.cpp
// compile with: /clr:pure /c
__declspec(dllexport) int g2 = 0;   // C3389
```