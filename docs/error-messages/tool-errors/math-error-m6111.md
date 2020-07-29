---
title: Matematik Hatası M6111
ms.date: 11/04/2016
f1_keywords:
- M6111
helpviewer_keywords:
- M6111
ms.assetid: c0fc13f8-33c8-4e3f-a440-126cc623441b
ms.openlocfilehash: 986c0e53edcddfc47eb9ba970f3c32385e0a57d9
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87225195"
---
# <a name="math-error-m6111"></a>Matematik Hatası M6111

yığın yetersiz

Kayan nokta işlemi 8087/287/387 Eşişlemcisi veya öykünücü üzerinde bir yığın üzerinde yetersizlik ile sonuçlandı.

Bu hata genellikle değer döndürmeyen bir işleve yapılan çağrı nedeniyle oluşur **`long double`** . Örneğin, aşağıdakiler derlendiğinde ve çalıştırıldığında bu hatayı üretir:

```
long double ld() {};
main ()
{
  ld();
}
```

Program 139 çıkış koduyla sona eriyor.
