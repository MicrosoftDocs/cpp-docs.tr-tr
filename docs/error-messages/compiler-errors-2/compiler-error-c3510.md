---
title: Derleyici Hatası C3510
ms.date: 11/04/2016
f1_keywords:
- C3510
helpviewer_keywords:
- C3510
ms.assetid: c48387bc-0300-4a4d-97f7-3fb90f82a451
ms.openlocfilehash: dbb65628aa6e0da94a91a59724ca8e1cd5b56491
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50620887"
---
# <a name="compiler-error-c3510"></a>Derleyici Hatası C3510

'type_lib' bağımlı tür kitaplığı bulunamıyor

[no_registry](../../preprocessor/no-registry.md) ve [auto_search](../../preprocessor/auto-search.md) için geçirilmiş `#import` ancak derleyicinin başvurulan tür kitaplığının bulmayı tamamlayamadı.

Bu hatayı çözmek için tüm tür kitaplıkları ve başvurulan tür kitaplıkları derleyiciye kullanılabilir olduğundan emin olun.

Aşağıdaki örnek, C3510 oluşturur:

Aşağıdaki iki tür kitaplıklarını oluşturulmuş ve bu C3510a.tlb silindi veya yolu üzerinde değildir.

```
// C3510a.idl
[uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12b")]
library C3510aLib
{
   [uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12c")]
   enum E_C3510
   {
      one, two, three
   };
};
```

Ve ardından ikinci tür kitaplığı kaynak kodunu:

```
// C3510b.idl
// post-build command: del /f C3510a.tlb
[uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12e")]
library C3510bLib
{
   importlib ("C3510a.tlb");
   [uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12d")]
   struct S_C3510 {
      enum E_C3510 e;
   };
};
```

Ve ardından istemci kodu:

```
// C3510.cpp
#import "c3510b.tlb" no_registry auto_search   // C3510
int main() {
   C3510aLib::S_C4336 ccc;
}
```