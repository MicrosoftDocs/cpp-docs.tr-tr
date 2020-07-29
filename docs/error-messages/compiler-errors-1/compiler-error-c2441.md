---
title: Derleyici hatası C2441
ms.date: 11/04/2016
f1_keywords:
- C2441
helpviewer_keywords:
- C2441
ms.assetid: ffbd6573-777a-48dd-892f-5cf4a758dcab
ms.openlocfilehash: aa55392e9f58caa4292cf5f96ef97f65a53bf913
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87207959"
---
# <a name="compiler-error-c2441"></a>Derleyici hatası C2441

> '*değişken*': __declspec (Process) ile belirtilen bir simge/clr: Pure modunda const olmalıdır

## <a name="remarks"></a>Açıklamalar

**/Clr: Pure** ve **/clr: Safe** derleyici seçenekleri Visual Studio 2015 ' de kullanımdan kaldırılmıştır ve Visual Studio 2017 ' de desteklenmez.

Varsayılan olarak, değişkenler **/clr: Pure**altında uygulama etki alanına göre yapılır. `__declspec(process)` **/Clr: Pure** altında işaretlenen bir değişken, bir uygulama etki alanında değiştirildiyse ve başka bir uygulamada okunduğu hatalara açıktır.

Bu nedenle, derleyici işlem başına, **`const`** **/clr: Pure**altında olduğundan, yalnızca tüm uygulama etki alanlarında Salt okunabilir hale getirir.

Daha fazla bilgi için bkz. [Process](../../cpp/process.md) and [/clr (ortak dil çalışma zamanı derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek C2441 oluşturur.

```cpp
// C2441.cpp
// compile with: /clr:pure /c
__declspec(process) int i;   // C2441
__declspec(process) const int j = 0;   // OK
```
