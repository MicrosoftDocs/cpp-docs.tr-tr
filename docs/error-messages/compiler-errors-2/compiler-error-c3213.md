---
title: Derleyici Hatası C3213
ms.date: 11/04/2016
f1_keywords:
- C3213
helpviewer_keywords:
- C3213
ms.assetid: 1f079e36-b3e9-40f8-8e95-08eeba3adc82
ms.openlocfilehash: 1b08b0ef5b8fefcfa1dd55ef3a16ee4ef5d027e0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62182515"
---
# <a name="compiler-error-c3213"></a>Derleyici Hatası C3213

temel sınıf 'taban_türü' 'derived_type' daha az erişilebilir

Görünür bir derlemeden bir tür, genel olarak görülecek temel sınıfları kullanmanız gerekir.

Aşağıdaki örnek, C3213 oluşturur:

```
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