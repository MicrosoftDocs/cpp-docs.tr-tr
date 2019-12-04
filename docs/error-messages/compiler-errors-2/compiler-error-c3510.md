---
title: Derleyici hatası C3510
ms.date: 11/04/2016
f1_keywords:
- C3510
helpviewer_keywords:
- C3510
ms.assetid: c48387bc-0300-4a4d-97f7-3fb90f82a451
ms.openlocfilehash: 3f9dea77b739aa59474e60cf852fff2577ab6ba9
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74753633"
---
# <a name="compiler-error-c3510"></a>Derleyici hatası C3510

' type_lib ' bağımlı tür kitaplığı bulunamıyor

[no_registry](../../preprocessor/no-registry.md) ve [auto_search](../../preprocessor/auto-search.md) `#import` geçirildi, ancak derleyici başvurulan bir tür kitaplığını bulamadı.

Bu hatayı çözmek için, tüm tür kitaplıklarının ve başvurulan tür kitaplıklarının derleyici için kullanılabilir olduğundan emin olun.

Aşağıdaki örnek C3510 oluşturur:

Aşağıdaki iki tür kitaplıklarının oluşturulduğunu ve bu C3510a. tlb ' nin, yolda silindiğini ya da olmadığını varsayın.

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

İkinci tür kitaplığı için kaynak kodu:

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

```cpp
// C3510.cpp
#import "c3510b.tlb" no_registry auto_search   // C3510
int main() {
   C3510aLib::S_C4336 ccc;
}
```
