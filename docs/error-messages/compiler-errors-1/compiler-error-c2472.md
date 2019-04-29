---
title: Derleyici Hatası C2472
ms.date: 11/04/2016
f1_keywords:
- C2472
helpviewer_keywords:
- C2472
ms.assetid: 3b36bcdc-2ba5-4357-ab88-7545ba0551cd
ms.openlocfilehash: d2f104bb61915f8d19d5fff22eea17929c0e8d74
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62350916"
---
# <a name="compiler-error-c2472"></a>Derleyici Hatası C2472

> '*işlevi*' yönetilen kod içinde üretilemez: '*ileti*'; karma görüntü üretmek için/CLR ile derleyin

## <a name="remarks"></a>Açıklamalar

Yönetilen kod tarafından desteklenmeyen türler bir saf ortak dil çalışma zamanı (CLR) ortamında kullanıldığında, bu hata oluşur. Derleme **/CLR** hatayı gidermek için.

**/CLR: pure** ve **/CLR: safe** derleyici seçenekleri Visual Studio 2015'te kullanım dışı ve Visual Studio 2017'de desteklenmiyor.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C2472 oluşturur.

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

- [/clr (Ortak Dil Çalışma Zamanı Derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md)
