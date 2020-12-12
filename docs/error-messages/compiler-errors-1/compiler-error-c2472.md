---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2472'
title: Derleyici hatası C2472
ms.date: 11/04/2016
f1_keywords:
- C2472
helpviewer_keywords:
- C2472
ms.assetid: 3b36bcdc-2ba5-4357-ab88-7545ba0551cd
ms.openlocfilehash: a1d4d668c1e7151771a2df85e888384c6c3ea028
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97164503"
---
# <a name="compiler-error-c2472"></a>Derleyici hatası C2472

> '*Function*', yönetilen kodda üretilemiyor: '*Message*'; Karma görüntü üretmek için/clr ile derleyin

## <a name="remarks"></a>Açıklamalar

Bu hata, yönetilen kod tarafından desteklenmeyen türler, saf ortak dil çalışma zamanı (CLR) ortamında kullanıldığında oluşur. Hatayı çözümlemek için **/clr** ile derleyin.

**/Clr: Pure** ve **/clr: Safe** derleyici seçenekleri Visual Studio 2015 ' de kullanımdan kaldırılmıştır ve Visual Studio 2017 ' de desteklenmez.

## <a name="example"></a>Örnek

Aşağıdaki örnek C2472 oluşturur.

```cpp
// C2472.cpp
// compile with: /clr:pure
// C2472 expected

#include <cstdlib>

int main()
{
   int * __ptr32 p32;
   int * __ptr64 p64;

   p32 = (int * __ptr32)malloc(4);
   p64 = p32;
}
```

## <a name="see-also"></a>Ayrıca bkz.

- [/clr (ortak dil çalışma zamanı derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md)
