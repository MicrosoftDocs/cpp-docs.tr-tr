---
title: Derleyici hatası C2663
ms.date: 11/04/2016
f1_keywords:
- C2663
helpviewer_keywords:
- C2663
ms.assetid: 1e93e368-fd52-42bf-9908-9b6df467c8c9
ms.openlocfilehash: f9746ecb41e873fb1d929a939c78f1817dc0e2f9
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87220281"
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
