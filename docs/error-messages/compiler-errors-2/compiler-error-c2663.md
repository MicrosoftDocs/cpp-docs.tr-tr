---
title: Derleyici hatası C2663
ms.date: 11/04/2016
f1_keywords:
- C2663
helpviewer_keywords:
- C2663
ms.assetid: 1e93e368-fd52-42bf-9908-9b6df467c8c9
ms.openlocfilehash: f07b63202d8f171dfb69f4bb294b392152b9290b
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74756038"
---
# <a name="compiler-error-c2663"></a>Derleyici hatası C2663

' function ': sayı aşırı yüklemelerinin ' this ' işaretçisi için geçerli dönüştürmesi yok

Derleyici, üye işlevinin aşırı yüklenmiş sürümlerinden hiçbirine `this` dönüştüremedi.

Bu hata, bir `const` nesnesi üzerinde`const` olmayan bir üye işlevi çağırarak oluşabilir.  Olası çözümler:

1. Nesne bildiriminden `const` kaldırın.

1. Üye işlev aşırı yüklemelerinin birine `const` ekleyin.

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
