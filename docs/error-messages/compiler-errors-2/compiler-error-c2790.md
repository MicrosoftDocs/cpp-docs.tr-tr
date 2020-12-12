---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2790'
title: Derleyici hatası C2790
ms.date: 11/04/2016
f1_keywords:
- C2790
helpviewer_keywords:
- C2790
ms.assetid: 38d4fce1-ba00-413d-8bc1-e8aa43d7bc1f
ms.openlocfilehash: 0913b87f40e7f4ad2ecccb333e67bb0d76b4afde
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97297816"
---
# <a name="compiler-error-c2790"></a>Derleyici hatası C2790

' Super ': Bu anahtar sözcük yalnızca sınıf üye işlevinin gövdesi içinde kullanılabilir

Bu hata iletisi, Kullanıcı bir üye işlev bağlamı dışında [süper](../../cpp/super.md) anahtar sözcüğünü kullanmaya çalışırsa görüntülenir.

Aşağıdaki örnek C2790 oluşturur:

```cpp
// C2790.cpp
void f() {
   __super::g();   // C2790
}
```
