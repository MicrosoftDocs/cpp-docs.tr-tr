---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 4) C4336'
title: Derleyici Uyarısı (düzey 4) C4336
ms.date: 11/04/2016
f1_keywords:
- C4336
helpviewer_keywords:
- C4336
ms.assetid: 93f199dd-d6dd-42c0-82d8-c12d101a7235
ms.openlocfilehash: d41ca5584864327b3012e79af97f2857e3f93d42
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97257725"
---
# <a name="compiler-warning-level-4-c4336"></a>Derleyici Uyarısı (düzey 4) C4336

' type_lib2 ' öğesini içeri aktarmadan önce ' type_lib1 ' çapraz referanslı tür kitaplığını içeri aktarın

[#İmport](../../preprocessor/hash-import-directive-cpp.md) yönergesiyle bir tür kitaplığına başvuruldu. Ancak tür kitaplığı, ile başvurulmayan başka bir tür kitaplığına başvuru içeriyordu `#import` . Bu diğer. tlb dosyası derleyici tarafından bulundu.

Aşağıdaki iki dosyadan oluşturulan diskte belirtilen iki tür kitaplığı (midl.exe ile derlenen):

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

Aşağıdaki örnek C4336 oluşturur:

```cpp
// C4336.cpp
// compile with: /W4 /LD
// #import "C4336a.tlb"
#import "C4336b.tlb"   // C4336, uncomment previous line to resolve
```
