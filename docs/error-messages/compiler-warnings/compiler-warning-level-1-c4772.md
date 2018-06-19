---
title: Derleyici Uyarısı (düzey 1) C4772 | Microsoft Docs
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4772
dev_langs:
- C++
helpviewer_keywords:
- C4772
ms.assetid: dafe6fd8-9faf-41f5-9d66-a55838742c14
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cbdcfec8d36568c31c291a9de8f9af3aac821fc6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33282278"
---
# <a name="compiler-warning-level-1-c4772"></a>Derleyici Uyarısı (düzey 1) C4772

> \#içeri aktarma türü eksik bir tür kitaplığından başvurulan; '*eksik türü*' yer tutucu olarak kullanılan

Tür kitaplığı ile başvuruldu [#import](../../preprocessor/hash-import-directive-cpp.md) yönergesi. Ancak, tür kitaplığı ile başvurulmadı başka bir tür kitaplığı başvuru bulunan `#import`. Bu bir .tlb dosyası derleyici tarafından bulunamadı.

Kullanırsanız derleyici tür kitaplıklarının farklı dizinlerde bulamayacaksınız olduğunu unutmayın [/ı (ek içeren dizinler)](../../build/reference/i-additional-include-directories.md) derleyici seçeneği bu dizinlerin belirtin. Tür kitaplıkları farklı dizinlerde bulmak için derleyici istiyorsanız, bu dizinlerin PATH ortam değişkenine ekleyin.

Varsayılan olarak, bu uyarıyı hata olarak verilir. C4772 ile /W0 atlanması olamaz.

## <a name="example"></a>Örnek

İlk tür kitaplığı C4772 yeniden üretmek için gereken budur.

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

İkinci tür kitaplığı C4772 yeniden üretmek için gereken budur.

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