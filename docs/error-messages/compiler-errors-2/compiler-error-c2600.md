---
title: Derleyici Hatası C2600
ms.date: 11/04/2016
f1_keywords:
- C2600
helpviewer_keywords:
- C2600
ms.assetid: cce11943-ea01-4bee-a7b0-b67d24ec6493
ms.openlocfilehash: 4d9e94790c3f4b2fa0aaf36894f0b12c7134a9ed
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50500405"
---
# <a name="compiler-error-c2600"></a>Derleyici Hatası C2600

'function': (bildirilmiş sınıfta ilk) derleyicinin ürettiği özel üye işlevi tanımlanamıyor

Bir sınıf için oluşturucuları veya yıkıcıları gibi işlevleri tanımlanabilir üye önce bunlar sınıfta bildirilmesi gerekir. Hiçbiri sınıfta bildirilen, derleyici varsayılan oluşturucular ve Yıkıcılar (özel üye işlevleri olarak adlandırılır) oluşturabilir. Ancak, eşleşen bir bildirim olmadan Bu işlevlerden biri sınıfında tanımlarsanız, derleyici bir çakışma algılar.

Sınıf bildirimi içinde bu hatayı düzeltmek için sınıf bildirimi dışında tanımladığınız her üye işlevini bildirin.

Aşağıdaki örnek, C2600 oluşturur:

```
// C2600.cpp
// compile with: /c
class C {};
C::~C() {}   // C2600

class D {
   D::~D();
};

D::~D() {}
```