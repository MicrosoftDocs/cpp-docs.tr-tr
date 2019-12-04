---
title: Derleyici hatası C2149
ms.date: 11/04/2016
f1_keywords:
- C2149
helpviewer_keywords:
- C2149
ms.assetid: 7a106dab-d79f-41b9-85be-f36e86e4d2ab
ms.openlocfilehash: ec082040085f33c0516590623a270e27a0e88810
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74756480"
---
# <a name="compiler-error-c2149"></a>Derleyici hatası C2149

' tanımlayıcı ': adlandırılmış bit alanının genişliği sıfır olamaz

Bit alanları yalnızca adlandırıldıysanız sıfır genişliğine sahip olabilir.

Aşağıdaki örnek C2149 oluşturur:

```cpp
// C2149.cpp
// compile with: /c
struct C {
   int i : 0;   // C2149
   int j : 2;   // OK
};
```
