---
title: Derleyici Hatası C2663
ms.date: 11/04/2016
f1_keywords:
- C2663
helpviewer_keywords:
- C2663
ms.assetid: 1e93e368-fd52-42bf-9908-9b6df467c8c9
ms.openlocfilehash: d74326e49edd980896276e2c6e67526d8d769cb7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62360300"
---
# <a name="compiler-error-c2663"></a>Derleyici Hatası C2663

'function': sayı aşırı yüklemelere sahip 'this' işaretçisi için hiçbir geçerli dönüşümler

Derleyici değil dönüştüremedi `this` herhangi bir üye işlevin aşırı yüklenmiş sürümleri.

Bu hata olmayan bir çağırarak kaynaklanabilir`const` üzerinde üye işlevi bir `const` nesne.  Olası çözümler:

1. Kaldırma `const` gelen nesne bildirimi.

1. Ekleme `const` bir üye işlev aşırı yüklemeleri.

Aşağıdaki örnek, C2663 oluşturur:

```
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