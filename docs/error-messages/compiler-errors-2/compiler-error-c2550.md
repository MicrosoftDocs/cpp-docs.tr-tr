---
title: Derleyici Hatası C2550 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2550
dev_langs:
- C++
helpviewer_keywords:
- C2550
ms.assetid: 3293f53e-ee66-4035-920d-34e115c3a24c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dd132184a993f27ec04a913cfef2aed07f8bd4a8
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46062520"
---
# <a name="compiler-error-c2550"></a>Derleyici Hatası C2550

'identifier': oluşturucu başlatıcı listelerine yalnızca Oluşturucu tanımlarında izin verilir

Bir temel sınıf başlatıcı listesi bir oluşturucusu olmayan bir işlev tanımı üzerinde kullanılır.

Aşağıdaki örnek, C2550 oluşturur:

```
// C2550.cpp
// compile with: /c
class C {
public:
   C();
};

class D : public C {
public:
   D();
   void func();
};

void D::func() : C() {}  // C2550
D::D() : C() {}   // OK
```