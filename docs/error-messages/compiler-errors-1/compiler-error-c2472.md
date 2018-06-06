---
title: Derleyici Hatası C2472 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2472
dev_langs:
- C++
helpviewer_keywords:
- C2472
ms.assetid: 3b36bcdc-2ba5-4357-ab88-7545ba0551cd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 43279190847322fa2154c6faababdcd41b490eef
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34704866"
---
# <a name="compiler-error-c2472"></a>Derleyici Hatası C2472

> '*işlevi*' yönetilen kodda oluşturulamıyor: '*ileti*'; karışık bir görüntü oluşturmak için/CLR ile derleme

## <a name="remarks"></a>Açıklamalar

Yönetilen kod tarafından desteklenmeyen türleri içinde saf ortak dil çalışma zamanı (CLR) ortamı kullanıldığında bu hata meydana gelir. İle derleme **/CLR** hatayı gidermek için.

**/CLR: pure** ve **/CLR: safe** derleyici seçenekleri Visual Studio 2015'te kullanım dışı ve Visual Studio 2017 içinde desteklenmiyor.

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

- [/clr (Ortak Dil Çalışma Zamanı Derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md)
