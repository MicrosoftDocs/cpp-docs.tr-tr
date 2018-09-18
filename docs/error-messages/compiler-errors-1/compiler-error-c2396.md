---
title: Derleyici Hatası C2396 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2396
dev_langs:
- C++
helpviewer_keywords:
- C2396
ms.assetid: 1b515ef6-7af4-400f-b4ed-564313ea15f6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0d69dfc1e296532f00ce9f44a178a366dca41e2e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46061636"
---
# <a name="compiler-error-c2396"></a>Derleyici Hatası C2396

' your_type::operator'type'': CLR veya WinRT kullanıcı tanımlı dönüştürme functionnot geçerli. Dönüştürmek veya Dönüştür: 'T ^', 'T ^ %', 'T ^ &', burada T = 'your_type'

Bir Windows çalışma zamanı veya yönetilen türü bir dönüştürme işlevi türü dönüştürme işlevi içeren türle aynı olan en az bir parametre yok.

Aşağıdaki örnek, C2396 oluşturur ve bu sorunun nasıl gösterir:

```
// C2396.cpp
// compile with: /clr /c

ref struct Y {
   static operator int(char c);   // C2396

   // OK
   static operator int(Y^ hY);
   // or
   static operator Y^(char c);
};
```