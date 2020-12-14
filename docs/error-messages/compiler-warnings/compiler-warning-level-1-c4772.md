---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4772'
title: Derleyici Uyarısı (düzey 1) C4772
ms.date: 11/04/2016
f1_keywords:
- C4772
helpviewer_keywords:
- C4772
ms.assetid: dafe6fd8-9faf-41f5-9d66-a55838742c14
ms.openlocfilehash: 41fcbf3074cb1e51e06ba21a01a27eaf8ded1b31
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97228449"
---
# <a name="compiler-warning-level-1-c4772"></a>Derleyici Uyarısı (düzey 1) C4772

> \#İçeri aktarma, eksik bir tür kitaplığından bir türe başvurdu; '*eksik-tür*' yer tutucu olarak kullanıldı

[#İmport](../../preprocessor/hash-import-directive-cpp.md) yönergesiyle bir tür kitaplığına başvuruldu. Ancak tür kitaplığı, ile başvurulmayan başka bir tür kitaplığına başvuru içeriyordu `#import` . Bu diğer. tlb dosyası derleyici tarafından bulunamadı.

Bu dizinleri belirtmek için [/ı (ek Içerme dizinleri)](../../build/reference/i-additional-include-directories.md) derleyici seçeneğini kullanırsanız, derleyicinin farklı dizinlerde tür kitaplıklarını bulamayacağını unutmayın. Derleyicinin farklı dizinlerde tür kitaplıklarını bulmasını istiyorsanız, bu dizinleri PATH ortam değişkenine ekleyin.

Varsayılan olarak bu uyarı hata olarak verilir. C4772/W0ile bastırılamaz.

## <a name="example"></a>Örnek

Bu, C4772 yeniden üretmek için gereken ilk tür kitaplığıdır.

```IDL
// c4772a.idl
[uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12b")]
library C4772aLib
{
   [uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c100")]
   enum E_C4772a
   {
      one, two, three
   };
};
```

Bu, C4772 yeniden üretmek için gereken ikinci tür kitaplığıdır.

```IDL
// c4772b.idl
// post-build command: del /f C4772a.tlb
// C4772a.tlb is available when c4772b.tlb is built
[uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12d")]
library C4772bLib
{
   importlib ("c4772a.tlb");
   [uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12e")]
   struct S_C4772b
   {
      enum E_C4772a e;
   };
};
```

Aşağıdaki örnek C4772 oluşturur:

```cpp
// C4772.cpp
// assumes that C4772a.tlb is not available to the compiler
// #import "C4772a.tlb"
#import "C4772b.tlb"   // C4772 uncomment previous line to resolve
                       // and make sure c4772a.tlb is on disk
```
