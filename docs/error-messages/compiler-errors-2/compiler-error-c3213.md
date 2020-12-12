---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3213'
title: Derleyici hatası C3213
ms.date: 11/04/2016
f1_keywords:
- C3213
helpviewer_keywords:
- C3213
ms.assetid: 1f079e36-b3e9-40f8-8e95-08eeba3adc82
ms.openlocfilehash: 5ae16ffd94c6d300956bb2723ccbe8c16b0d6b3a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97291772"
---
# <a name="compiler-error-c3213"></a>Derleyici hatası C3213

' base_type ' temel sınıfı ' derived_type ' öğesinden daha az erişilebilir

Bir derlemeden görünebilen bir tür, herkese açık olarak görünen temel sınıfları kullanmalıdır.

Aşağıdaki örnek C3213 oluşturur:

```cpp
// C3213.cpp
// compile with: /clr
private ref struct privateG {
public:
   int i;
};

public ref struct publicG {
public:
   int i;
};

public ref struct V : public privateG {   // C3213
public:
   int j;
};

public ref struct W: public publicG {   // OK
public:
   int j;
};
```
