---
title: Derleyici Uyarısı (düzey 1) C4772
ms.date: 11/04/2016
f1_keywords:
- C4772
helpviewer_keywords:
- C4772
ms.assetid: dafe6fd8-9faf-41f5-9d66-a55838742c14
ms.openlocfilehash: 95243ab66d5d0296e1c316ff8dde7add75a030cd
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62385465"
---
# <a name="compiler-warning-level-1-c4772"></a>Derleyici Uyarısı (düzey 1) C4772

> \#içeri aktarma, bir eksik tür kitaplığından bir tür başvurulan; '*eksik tür*' yer tutucu olarak kullanılan

Bir tür kitaplığı ile başvuruldu [#import](../../preprocessor/hash-import-directive-cpp.md) yönergesi. Ancak, tür kitaplığı ile başvurulmadı başka bir tür kitaplığına bir başvuruyu bulunan `#import`. Bu bir .tlb dosyasının derleyici tarafından nebyl nalezen.

Kullanırsanız, derleyicinin tür kitaplıklarını farklı dizinlerde bulmaz olduğunu unutmayın [/ı (ek içeren dizinler)](../../build/reference/i-additional-include-directories.md) bu dizinlerin belirtmek için derleyici seçeneği. Derleyicinin tür kitaplıklarını farklı dizinlerde bulmak istiyorsanız, bu dizinler için yol ortam değişkenine ekleyin.

Varsayılan olarak, bu uyarıyı hata olarak verilir. C4772 /W0 ile atlanması olamaz.

## <a name="example"></a>Örnek

İlk tür kitaplığı C4772 üretmek için gereken budur.

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

İkinci tür kitaplığı C4772 üretmek için gereken budur.

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

Aşağıdaki örnek, C4772 oluşturur:

```cpp
// C4772.cpp
// assumes that C4772a.tlb is not available to the compiler
// #import "C4772a.tlb"
#import "C4772b.tlb"   // C4772 uncomment previous line to resolve
                       // and make sure c4772a.tlb is on disk
```