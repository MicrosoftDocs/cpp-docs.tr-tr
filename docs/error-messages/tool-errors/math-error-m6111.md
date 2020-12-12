---
description: 'Daha fazla bilgi edinin: matematik hatası M6111'
title: Matematik Hatası M6111
ms.date: 11/04/2016
f1_keywords:
- M6111
helpviewer_keywords:
- M6111
ms.assetid: c0fc13f8-33c8-4e3f-a440-126cc623441b
ms.openlocfilehash: 9bf2d620a0df18752b74aaacd4d2415510407f0f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97244348"
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
