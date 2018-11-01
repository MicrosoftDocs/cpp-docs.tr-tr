---
title: Derleyici Uyarısı (düzey 4) C4337
ms.date: 11/04/2016
f1_keywords:
- C4337
helpviewer_keywords:
- C4337
ms.assetid: 70bc72d9-aac5-45cd-abd3-ebe42a05897b
ms.openlocfilehash: 2bfa5f9b30fa0325df1c3655ded53ab0525449c3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50479566"
---
# <a name="compiler-warning-level-4-c4337"></a>Derleyici Uyarısı (düzey 4) C4337

'typelib2' çapraz başvurulan tür kitaplığında 'typelib1' otomatik olarak içeri aktarılıyor

Auto_search özniteliği [#import directive](../../preprocessor/hash-import-directive-cpp.md) örtük olarak içeri aktarılacak tür kitaplığını neden oldu.

Verilen iki tür kitaplıkları (midl.exe'yi ile derlenmiş) aşağıdaki iki dosyalarından oluşturulan diskte:

```
// C4337a.idl
[
  uuid(F87070BA-C6D9-405C-A8E4-8CD9CA25C12B)
]
library C4337aLib
{
   [uuid(F87070BA-C6D9-405C-A8E4-8CD9CA25C12C)]
   enum E_C4337a
   {
      one = 0,
      two = 1,
      three = 2
    };
};
```

ve ardından ikinci .idl dosyası

```
// C4337b.idl
[
   uuid(F87070BA-C6D9-405C-A8E4-8CD9CA25C12D)
]

library C4337bLib
{
   importlib("c4337a.tlb");

   [uuid(F87070BA-C6D9-405C-A8E4-8CD9CA25C12E)]
   struct S_C4337b
   {
      enum E_C4337a e;
   };
};
```

Aşağıdaki örnek, C4337 oluşturur:

```
// C4337.cpp
// compile with: /W4 /LD
#import "c4337b.tlb" auto_search   // C4337
// explicitly #import all type libraries to resolve
// #import "C4337a.tlb"
// #import "C4337b.tlb"
```