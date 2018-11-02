---
title: Önemli hata C1311
ms.date: 11/04/2016
f1_keywords:
- C1311
helpviewer_keywords:
- C1311
ms.assetid: 6590a06c-ce9d-4f17-8f62-c809343143b8
ms.openlocfilehash: ba2b797c9bf521533e7c2ccff8d358b6216d392f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50637911"
---
# <a name="fatal-error-c1311"></a>Önemli hata C1311

COFF biçimi 'var' numara miktarında bir adresi statik olarak başlatılamıyor

Değeri derleme zamanında bilinen olmayan bir adresi statik olarak küçüktür dört baytlık depolama türü olan bir değişkene atanamaz.

Kod üzerinde değilse bu hata oluşabilir geçerli C++.

Aşağıdaki örnek, C1311 neden olabilecek bir durumu gösterir.

```
char c = (char)"Hello, world";   // C1311
char *d = (char*)"Hello, world";   // OK
```