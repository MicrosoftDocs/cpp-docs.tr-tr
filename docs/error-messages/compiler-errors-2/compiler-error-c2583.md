---
title: Derleyici Hatası C2583 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2583
dev_langs:
- C++
helpviewer_keywords:
- C2583
ms.assetid: b1c952dc-872c-47e4-9fc8-4dd72bcee6f9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3aad4a818d0c8869681f9a2f4c4ace0edb63cd02
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46117536"
---
# <a name="compiler-error-c2583"></a>Derleyici Hatası C2583

'identifier': ' const/volatile' 'this' işaretçisi oluşturucular/yok ediciler için geçersizdir

Bir oluşturucu veya yıkıcı bildirilen `const` veya `volatile`. Buna izin verilmez.

Aşağıdaki örnek, C2583 oluşturur:

```
// C2583.cpp
// compile with: /c
class A {
public:
   int i;
   A() const;   // C2583

   // try the following line instead
   // A();
};
```