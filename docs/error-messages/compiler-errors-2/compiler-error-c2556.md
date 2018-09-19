---
title: Derleyici Hatası C2556 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2556
dev_langs:
- C++
helpviewer_keywords:
- C2556
ms.assetid: fc4399ad-45b3-49fd-be1f-0b13956a595a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 880234d1d11556b8882bfd564fdf64bc587d56ae
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46107807"
---
# <a name="compiler-error-c2556"></a>Derleyici Hatası C2556

'identifier': aşırı yüklenmiş işlevler yalnızca dönüş türüne göre farklılık gösterir

Aşırı yüklenmiş işlevler aynı parametre listesi ancak farklı dönüş türlerine sahip. Her aşırı yüklenmiş işlev ayrı biçimsel parametre listesi olmalıdır.

Aşağıdaki örnek, C2556 oluşturur:

```
// C2556.cpp
// compile with: /c
class C {
   int func();
   double func();   // C2556
   int func(int i);   // ok parameter lists differ
};
```