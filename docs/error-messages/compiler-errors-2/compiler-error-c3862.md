---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3862'
title: Derleyici hatası C3862
ms.date: 11/04/2016
f1_keywords:
- C3862
helpviewer_keywords:
- C3862
ms.assetid: ba547366-4189-4077-8c00-ab45e08a9533
ms.openlocfilehash: b8955a69bcd04c0a40aed8fab722c6c734bfa65b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97222898"
---
# <a name="compiler-error-c3862"></a>Derleyici hatası C3862

> '*Function*': yönetilmeyen bir işlev/clr: pure veya/clr: Safe ile derlenemez

## <a name="remarks"></a>Açıklamalar

**/Clr: Pure** ve **/clr: Safe** derleyici seçenekleri Visual Studio 2015 ' de kullanımdan kaldırılmıştır ve Visual Studio 2017 ' de desteklenmez.

**/Clr: Pure** veya **/clr: Safe** ile bir derleme, yerel (yönetilmeyen) kod içermeyen BIR görüntü olan yalnızca MSIL görüntüsü oluşturur.  Bu nedenle, `unmanaged` pragmayı **/clr: Pure** veya **/clr: Safe** derlemesinde kullanamazsınız.

Daha fazla bilgi için bkz. [/clr (ortak dil çalışma zamanı derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md) ve [yönetilen, yönetilmeyen](../../preprocessor/managed-unmanaged.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek C3862 oluşturur:

```cpp
// C3862.cpp
// compile with: /clr:pure /c
#pragma unmanaged
void f() {}   // C3862
```
