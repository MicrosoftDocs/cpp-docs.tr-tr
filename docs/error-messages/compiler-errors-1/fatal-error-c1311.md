---
title: Önemli hata C1311 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1311
dev_langs:
- C++
helpviewer_keywords:
- C1311
ms.assetid: 6590a06c-ce9d-4f17-8f62-c809343143b8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d93aa28d0cef3c07fd469349d485c4009fa4771d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46091068"
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