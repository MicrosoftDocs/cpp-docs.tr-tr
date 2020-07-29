---
title: Derleyici hatası C3389
ms.date: 11/04/2016
f1_keywords:
- C3389
helpviewer_keywords:
- C3389
ms.assetid: eaaffe17-23f2-413c-b1ad-f7220cfa1334
ms.openlocfilehash: 823b28deae3e3cfc18cdad8d37007bf8e8cff494
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87221061"
---
# <a name="compiler-error-c3389"></a>Derleyici hatası C3389

> __declspec (*anahtar sözcük*)/clr: pure veya/clr: Safe ile kullanılamaz

## <a name="remarks"></a>Açıklamalar

**/Clr: Pure** ve **/clr: Safe** derleyici seçenekleri Visual Studio 2015 ' de kullanımdan kaldırılmıştır ve Visual Studio 2017 ' de desteklenmez.

Kullanılan [__declspec](../../cpp/declspec.md) değiştirici, işlem başına durumu gösterir.  [/clr: Pure](../../build/reference/clr-common-language-runtime-compilation.md) , [AppDomain](../../cpp/appdomain.md) başına durum belirtir.  Bu nedenle, `keyword` **`__declspec`** değiştirici ve derleme ile **/clr: Pure** ile bir değişken bildirmek için izin verilmez.

## <a name="example"></a>Örnek

Aşağıdaki örnek C3389 oluşturur:

```cpp
// C3389.cpp
// compile with: /clr:pure /c
__declspec(dllexport) int g2 = 0;   // C3389
```
