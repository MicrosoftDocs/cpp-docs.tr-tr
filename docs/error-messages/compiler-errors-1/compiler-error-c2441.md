---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2441'
title: Derleyici hatası C2441
ms.date: 11/04/2016
f1_keywords:
- C2441
helpviewer_keywords:
- C2441
ms.assetid: ffbd6573-777a-48dd-892f-5cf4a758dcab
ms.openlocfilehash: d7a6073be821fcd2717caae258c5b3f397fb3f87
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97189736"
---
# <a name="compiler-error-c2441"></a>Derleyici hatası C2441

> '*değişken*': __declspec (Process) ile belirtilen bir simge/clr: Pure modunda const olmalıdır

## <a name="remarks"></a>Açıklamalar

**/Clr: Pure** ve **/clr: Safe** derleyici seçenekleri Visual Studio 2015 ' de kullanımdan kaldırılmıştır ve Visual Studio 2017 ' de desteklenmez.

Varsayılan olarak, değişkenler **/clr: Pure** altında uygulama etki alanına göre yapılır. `__declspec(process)` **/Clr: Pure** altında işaretlenen bir değişken, bir uygulama etki alanında değiştirildiyse ve başka bir uygulamada okunduğu hatalara açıktır.

Bu nedenle, derleyici işlem başına, **`const`** **/clr: Pure** altında olduğundan, yalnızca tüm uygulama etki alanlarında Salt okunabilir hale getirir.

Daha fazla bilgi için bkz. [Process](../../cpp/process.md) and [/clr (ortak dil çalışma zamanı derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek C2441 oluşturur.

```cpp
// C2441.cpp
// compile with: /clr:pure /c
__declspec(process) int i;   // C2441
__declspec(process) const int j = 0;   // OK
```
