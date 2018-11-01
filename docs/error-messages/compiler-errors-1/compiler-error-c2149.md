---
title: Derleyici Hatası C2149
ms.date: 11/04/2016
f1_keywords:
- C2149
helpviewer_keywords:
- C2149
ms.assetid: 7a106dab-d79f-41b9-85be-f36e86e4d2ab
ms.openlocfilehash: 62eca9730b28f83cea39d5c6606d4bb94ce885dd
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50445909"
---
# <a name="compiler-error-c2149"></a>Derleyici Hatası C2149

'identifier': adlandırılmış bit alanının genişliği sıfır olamaz

Bit alanları yalnızca adlandırılmamış Sıfır Genişlik olabilir.

Aşağıdaki örnek, C2149 oluşturur:

```
// C2149.cpp
// compile with: /c
struct C {
   int i : 0;   // C2149
   int j : 2;   // OK
};
```