---
title: Derleyici hatası C3389
ms.date: 11/04/2016
f1_keywords:
- C3389
helpviewer_keywords:
- C3389
ms.assetid: eaaffe17-23f2-413c-b1ad-f7220cfa1334
ms.openlocfilehash: b166096390169939f01bcb976a57612f10f7df2e
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80201142"
---
# <a name="compiler-error-c3389"></a>Derleyici hatası C3389

> __declspec (*anahtar sözcük*)/clr: pure veya/clr: Safe ile kullanılamaz

## <a name="remarks"></a>Açıklamalar

**/Clr: Pure** ve **/clr: Safe** derleyici seçenekleri Visual Studio 2015 ' de kullanımdan kaldırılmıştır ve Visual Studio 2017 ' de desteklenmez.

Kullanılan [__declspec](../../cpp/declspec.md) değiştirici, işlem başına durumu gösterir.  [/clr: Pure](../../build/reference/clr-common-language-runtime-compilation.md) , [AppDomain](../../cpp/appdomain.md) başına durum belirtir.  Bu nedenle, `keyword` **__declspec** değiştiricisiyle bir değişken bildirmek ve **/clr: Pure** ile derlemek için izin verilmez.

## <a name="example"></a>Örnek

Aşağıdaki örnek C3389 oluşturur:

```cpp
// C3389.cpp
// compile with: /clr:pure /c
__declspec(dllexport) int g2 = 0;   // C3389
```
