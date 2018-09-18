---
title: Derleyici Uyarısı (düzey 4) C4336 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4336
dev_langs:
- C++
helpviewer_keywords:
- C4336
ms.assetid: 93f199dd-d6dd-42c0-82d8-c12d101a7235
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0ce0bc5a8a3df26a330de55c331d46b1f0c1d692
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46051177"
---
# <a name="compiler-warning-level-4-c4336"></a>Derleyici Uyarısı (düzey 4) C4336

Çapraz başvurulan tür kitaplığı 'type_lib1' 'type_lib2' içeri aktarmadan önce içeri aktarma

Bir tür kitaplığı ile başvuruldu [#import](../../preprocessor/hash-import-directive-cpp.md) yönergesi. Ancak, tür kitaplığı ile başvurulmadı başka bir tür kitaplığına bir başvuruyu bulunan `#import`. Bu bir .tlb dosyasının derleyici tarafından bulunamadı.

Verilen iki tür kitaplıkları (midl.exe'yi ile derlenmiş) aşağıdaki iki dosyalarından oluşturulan diskte:

```
// c4336a.idl
[uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12b")]
library c4336aLib
{
   [uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12c")]
   enum E_C4336
   {
      one, two, three
   };
};
```

İkinci tür kitaplığı:

```
// c4336b.idl
[uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12d")]
library C4336bLib
{
   importlib ("c4336a.tlb");
   [uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12e")]
   struct S_C4336
   {
      enum E_C4336 e;
   };
};
```

Aşağıdaki örnek, C4336 oluşturur:

```
// C4336.cpp
// compile with: /W4 /LD
// #import "C4336a.tlb"
#import "C4336b.tlb"   // C4336, uncomment previous line to resolve
```