---
title: Derleyici hatası C2441
ms.date: 11/04/2016
f1_keywords:
- C2441
helpviewer_keywords:
- C2441
ms.assetid: ffbd6573-777a-48dd-892f-5cf4a758dcab
ms.openlocfilehash: 4e5d5335717ec77c61069ad08e209f9e1851dc2f
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80205315"
---
# <a name="compiler-error-c2441"></a>Derleyici hatası C2441

> '*değişken*': __declspec (Process) ile belirtilen bir simge/clr: Pure modunda const olmalıdır

## <a name="remarks"></a>Açıklamalar

**/Clr: Pure** ve **/clr: Safe** derleyici seçenekleri Visual Studio 2015 ' de kullanımdan kaldırılmıştır ve Visual Studio 2017 ' de desteklenmez.

Varsayılan olarak, değişkenler **/clr: Pure**altında uygulama etki alanına göre yapılır. **/Clr: Pure** altında `__declspec(process)` işaretli bir değişken, bir uygulama etki alanında değiştirildiyse ve başka bir uygulamada okunduğu hatalara açıktır.

Bu nedenle, derleyici işlem başına, **/clr: Pure**altında `const` ve yalnızca tüm uygulama etki alanlarında salt okunurdur.

Daha fazla bilgi için bkz. [Process](../../cpp/process.md) and [/clr (ortak dil çalışma zamanı derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek C2441 oluşturur.

```cpp
// C2441.cpp
// compile with: /clr:pure /c
__declspec(process) int i;   // C2441
__declspec(process) const int j = 0;   // OK
```
