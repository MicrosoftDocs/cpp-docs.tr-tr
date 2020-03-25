---
title: Matematik Hatası M6111
ms.date: 11/04/2016
f1_keywords:
- M6111
helpviewer_keywords:
- M6111
ms.assetid: c0fc13f8-33c8-4e3f-a440-126cc623441b
ms.openlocfilehash: e8abedf6a326a826d0c8ac513b15037c8bf89bce
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80173697"
---
# <a name="math-error-m6111"></a>Matematik Hatası M6111

yığın yetersiz

Kayan nokta işlemi 8087/287/387 Eşişlemcisi veya öykünücü üzerinde bir yığın üzerinde yetersizlik ile sonuçlandı.

Bu hata genellikle değer döndürmeyen bir `long double` işlevine yapılan çağrıdan kaynaklanır. Örneğin, aşağıdakiler derlendiğinde ve çalıştırıldığında bu hatayı üretir:

```
long double ld() {};
main ()
{
  ld();
}
```

Program 139 çıkış koduyla sona eriyor.
