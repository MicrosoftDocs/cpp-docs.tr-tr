---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2600'
title: Derleyici hatası C2600
ms.date: 11/04/2016
f1_keywords:
- C2600
helpviewer_keywords:
- C2600
ms.assetid: cce11943-ea01-4bee-a7b0-b67d24ec6493
ms.openlocfilehash: fbd99cb50bc3afc748e1d3b2e954c584a7cef78b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97120029"
---
# <a name="compiler-error-c2600"></a>Derleyici hatası C2600

' function ': derleyicinin ürettiği özel üye işlev tanımlanamıyor (önce sınıfta bildirilmelidir)

Bir sınıf için oluşturucular veya Yıkıcılar gibi üye işlevleri tanımlanmadan önce, sınıfında bildirilmelidir. Derleyici, sınıfında bildirilmemiş varsayılan oluşturucular ve Yıkıcılar (özel üye işlevleri olarak adlandırılır) oluşturabilir. Ancak, bu işlevlerden birini sınıfında eşleşen bir bildirim olmadan tanımlarsanız, derleyici bir çakışma algılar.

Bu hatayı onarmak için, sınıf bildiriminde, sınıf bildirimi dışında tanımladığınız her üye işlevini bildirin.

Aşağıdaki örnek C2600 oluşturur:

```cpp
// C2600.cpp
// compile with: /c
class C {};
C::~C() {}   // C2600

class D {
   D::~D();
};

D::~D() {}
```
