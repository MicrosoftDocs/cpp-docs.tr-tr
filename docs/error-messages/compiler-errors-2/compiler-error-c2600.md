---
title: Derleyici Hatası C2600 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2600
dev_langs:
- C++
helpviewer_keywords:
- C2600
ms.assetid: cce11943-ea01-4bee-a7b0-b67d24ec6493
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c1846cefa78c8df13e8ca3c1a7fbc142ba2bf6ad
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46022090"
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