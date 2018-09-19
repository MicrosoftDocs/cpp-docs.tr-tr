---
title: Derleyici Hatası C2663 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2663
dev_langs:
- C++
helpviewer_keywords:
- C2663
ms.assetid: 1e93e368-fd52-42bf-9908-9b6df467c8c9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fed35dcce056eb3d2a660c154e94b8058563dba7
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46083697"
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