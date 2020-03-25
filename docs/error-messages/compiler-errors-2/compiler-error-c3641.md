---
title: Derleyici hatası C3641
ms.date: 11/04/2016
f1_keywords:
- C3641
helpviewer_keywords:
- C3641
ms.assetid: e8d3613e-5e8d-46fe-a516-eb7d1de7cd21
ms.openlocfilehash: 44356fb1a1818a02102d23e6b308457f2f39506b
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80200518"
---
# <a name="compiler-error-c3641"></a>Derleyici hatası C3641

> '*Function*':/clr: pure veya/clr: Safe ile derlenen işlev için geçersiz çağrı kuralı ' calling_convention '

## <a name="remarks"></a>Açıklamalar

**/Clr: Pure** ve **/clr: Safe** derleyici seçenekleri Visual Studio 2015 ' de kullanımdan kaldırılmıştır ve Visual Studio 2017 ' de desteklenmez.

[/Clr: Pure](../../build/reference/clr-common-language-runtime-compilation.md)ile yalnızca [__clrcall](../../cpp/clrcall.md) çağırma kuralına izin verilir.

## <a name="example"></a>Örnek

Aşağıdaki örnek C3641 oluşturur:

```cpp
// C3641.cpp
// compile with: /clr:pure /c
void __cdecl f() {}   // C3641
```
