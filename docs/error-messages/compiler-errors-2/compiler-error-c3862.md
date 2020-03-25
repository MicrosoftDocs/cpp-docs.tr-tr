---
title: Derleyici hatası C3862
ms.date: 11/04/2016
f1_keywords:
- C3862
helpviewer_keywords:
- C3862
ms.assetid: ba547366-4189-4077-8c00-ab45e08a9533
ms.openlocfilehash: 0b9c1e1213949d7d700094caa6687232df881ce6
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80165489"
---
# <a name="compiler-error-c3862"></a>Derleyici hatası C3862

> '*Function*': yönetilmeyen bir işlev/clr: pure veya/clr: Safe ile derlenemez

## <a name="remarks"></a>Açıklamalar

**/Clr: Pure** ve **/clr: Safe** derleyici seçenekleri Visual Studio 2015 ' de kullanımdan kaldırılmıştır ve Visual Studio 2017 ' de desteklenmez.

**/Clr: Pure** veya **/clr: Safe** ile bir derleme, yerel (yönetilmeyen) kod içermeyen BIR görüntü olan yalnızca MSIL görüntüsü oluşturur.  Bu nedenle, **/clr: Pure** veya **/clr: Safe** derlemesinde `unmanaged` pragma kullanamazsınız.

Daha fazla bilgi için bkz. [/clr (ortak dil çalışma zamanı derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md) ve [yönetilen, yönetilmeyen](../../preprocessor/managed-unmanaged.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek C3862 oluşturur:

```cpp
// C3862.cpp
// compile with: /clr:pure /c
#pragma unmanaged
void f() {}   // C3862
```
