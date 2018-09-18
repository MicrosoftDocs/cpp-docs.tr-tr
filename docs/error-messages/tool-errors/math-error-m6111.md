---
title: Matematik hatası M6111 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- M6111
dev_langs:
- C++
helpviewer_keywords:
- M6111
ms.assetid: c0fc13f8-33c8-4e3f-a440-126cc623441b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 95a55ec6b7cdf0b6e4c15bd283dde77c610698fa
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46074831"
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