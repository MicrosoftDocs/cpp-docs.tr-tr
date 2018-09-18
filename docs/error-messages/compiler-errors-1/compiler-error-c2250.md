---
title: Derleyici Hatası C2250 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2250
dev_langs:
- C++
helpviewer_keywords:
- C2250
ms.assetid: f990986f-5c7d-4af4-a25c-b35540f1e217
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bee638b3e716460f54def3dc347810c874706708
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46070138"
---
# <a name="compiler-error-c2250"></a>Derleyici Hatası C2250

'identifier': 'class::member' öğesinin devralınması belirsiz

Türetilmiş bir sınıf sanal temel sınıfın sanal bir işlevin birden fazla geçersiz kılma devralır. Bu geçersiz kılma işlemleri türetilmiş sınıf içinde belirsiz olabilir.

Aşağıdaki örnek, C2286 oluşturur:

```
// C2250.cpp
// compile with: /c
// C2250 expected
struct V {
   virtual void vf();
};

struct A : virtual V {
   void vf();
};

struct B : virtual V {
   void vf();
};

struct D : A, B {
   // Uncomment the following line to resolve.
   // void vf();
};
```