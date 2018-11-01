---
title: Derleyici Hatası C3862
ms.date: 11/04/2016
f1_keywords:
- C3862
helpviewer_keywords:
- C3862
ms.assetid: ba547366-4189-4077-8c00-ab45e08a9533
ms.openlocfilehash: 2ba130862b1debbe2991ca7cbcae50192f900cd8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50446247"
---
# <a name="compiler-error-c3862"></a>Derleyici Hatası C3862

> '*işlevi*': / CLR ile yönetilmeyen bir işlev olarak derlenemez: pure veya/CLR: safe

## <a name="remarks"></a>Açıklamalar

**/CLR: pure** ve **/CLR: safe** derleyici seçenekleri Visual Studio 2015'te kullanım dışı ve Visual Studio 2017'de desteklenmiyor.

Bir derleme ile **/CLR: pure** veya **/CLR: safe** MSIL yalnızca görüntü, görüntünün yerel (yönetilmeyen) kod olmadan üretecektir.  Bu nedenle, kullanamazsınız `unmanaged` pragması yerleştirebilirsiniz bir **/CLR: pure** veya **/CLR: safe** derleme.

Daha fazla bilgi için [/CLR (ortak dil çalışma zamanı derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md) ve [yönetilen, yönetilmeyen](../../preprocessor/managed-unmanaged.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3862 oluşturur:

```cpp
// C3862.cpp
// compile with: /clr:pure /c
#pragma unmanaged
void f() {}   // C3862
```