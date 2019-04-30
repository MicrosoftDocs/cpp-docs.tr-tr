---
title: Matematik Hatası M6111
ms.date: 11/04/2016
f1_keywords:
- M6111
helpviewer_keywords:
- M6111
ms.assetid: c0fc13f8-33c8-4e3f-a440-126cc623441b
ms.openlocfilehash: 44f406881d64d13e23ca2c0911ee278c864a2c11
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62393414"
---
# <a name="math-error-m6111"></a>Matematik Hatası M6111

Yığında

Bir yığın underflow 8087/287/387 eşişlemcisi veya öykünücü, kayan noktalı bir işlemin sonuçlandı.

Bu hata genellikle bir çağrı tarafından neden bir `long double` işlev bir değer döndürmez. Örneğin, aşağıdaki bu hatayı derlenmiş ve çalışma oluşturur:

```
long double ld() {};
main ()
{
  ld();
}
```

Program çıkış kodu ile 139 sonlandırır.