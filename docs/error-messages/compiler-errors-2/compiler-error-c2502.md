---
title: Derleyici Hatası C2502 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2502
dev_langs:
- C++
helpviewer_keywords:
- C2502
ms.assetid: affa0b86-15fc-4e17-b7f2-6aad4a3771c4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f5e3197ca71ff277f2904666261e7d0546a9128f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46032540"
---
# <a name="compiler-error-c2502"></a>Derleyici Hatası C2502

'identifier': taban sınıfta çok fazla erişim değiştiricileri

Temel sınıfın birden fazla erişim değiştiricisi vardır. Yalnızca bir erişim belirleyici (`public`, `private`, veya `protected`) izin verilir.

Aşağıdaki örnek, C2502 oluşturur:

```
// C2502.cpp
// compile with: /c
class A { };
class B { };
class C : private public A { };   // C2502

// OK
class D : private A {};
class E : public A, private B {};
```