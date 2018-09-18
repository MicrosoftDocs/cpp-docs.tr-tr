---
title: Derleyici Hatası C2798 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2798
dev_langs:
- C++
helpviewer_keywords:
- C2798
ms.assetid: fb0cd861-b228-4f81-8090-e28344a727e0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 88241989d54e1a068b226b59091a381f531dee9e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46028863"
---
# <a name="compiler-error-c2798"></a>Derleyici Hatası C2798

'super::member' belirsiz

İle başvurulan üyesi birden fazla devralınan yapıları içeren [Süper](../../cpp/super.md). Hatayı düzeltin ya da:

- B1 veya B2 D. devralma listesinden kaldırılıyor

- B1 B2 de veri üyesinin adı değiştiriliyor.

Aşağıdaki örnek, C2798 oluşturur:

```
// C2798.cpp
struct B1 {
   int i;
};

struct B2 {
   int i;
};

struct D : B1, B2 {
   void g() {
      __super::i = 4; // C2798
   }
};
```