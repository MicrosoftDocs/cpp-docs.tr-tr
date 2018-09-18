---
title: Derleyici Hatası C3213 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3213
dev_langs:
- C++
helpviewer_keywords:
- C3213
ms.assetid: 1f079e36-b3e9-40f8-8e95-08eeba3adc82
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a23f61dc8170ff7cd5638d2b2f394d288f48c5f3
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46112986"
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