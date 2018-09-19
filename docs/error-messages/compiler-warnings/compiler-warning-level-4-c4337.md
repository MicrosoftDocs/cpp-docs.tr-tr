---
title: Derleyici Uyarısı (düzey 4) C4337 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4337
dev_langs:
- C++
helpviewer_keywords:
- C4337
ms.assetid: 70bc72d9-aac5-45cd-abd3-ebe42a05897b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d5b4e72f3dfda903a3d0f4563a730dc44411f79c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46016461"
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