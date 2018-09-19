---
title: Derleyici Hatası C2369 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2369
dev_langs:
- C++
helpviewer_keywords:
- C2369
ms.assetid: 2a3933f6-2313-40ff-800f-921b296fdbbf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4cce5784c0ff56498922d83ff61350a6c992c76c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46098194"
---
# <a name="compiler-error-c2369"></a>Derleyici Hatası C2369

'array': yeniden tanımlama; indisler farklı

Dizi ile farklı bir alt simge zaten bildirildi.

Aşağıdaki örnek, C2369 oluşturur:

```
// C2369.cpp
// compile with: /c
int a[10];
int a[20];   // C2369
int b[20];   // OK
```