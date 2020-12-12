---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2663'
title: Derleyici hatası C2663
ms.date: 11/04/2016
f1_keywords:
- C2663
helpviewer_keywords:
- C2663
ms.assetid: 1e93e368-fd52-42bf-9908-9b6df467c8c9
ms.openlocfilehash: 3e70e2d10b0a133769d92ce637bd9e5f4d44315a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97169989"
---
# <a name="compiler-error-c2663"></a>Derleyici hatası C2663

' function ': sayı aşırı yüklemelerinin ' this ' işaretçisi için geçerli dönüştürmesi yok

Derleyici, **`this`** üye işlevinin aşırı yüklenmiş sürümlerinden hiçbirine dönüştürülemedi.

Bu hata, **`const`** bir nesne üzerinde üye olmayan bir işlev çağırarak oluşabilir **`const`** .  Olası çözümler:

1. **`const`** Nesne bildiriminden öğesini kaldırın.

1. **`const`** Üye işlev aşırı yüklemelerinin birine ekleyin.

Aşağıdaki örnek C2663 oluşturur:

```cpp
// C2663.cpp
struct C {
   void f() volatile {}
   void f() {}
};

struct D {
   void f() volatile;
   void f() const {}
};

const C *pcc;
const D *pcd;

int main() {
   pcc->f();    // C2663
   pcd->f();    // OK
}
```
