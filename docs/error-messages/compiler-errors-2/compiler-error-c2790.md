---
title: Derleyici Hatası C2790
ms.date: 11/04/2016
f1_keywords:
- C2790
helpviewer_keywords:
- C2790
ms.assetid: 38d4fce1-ba00-413d-8bc1-e8aa43d7bc1f
ms.openlocfilehash: e377c18b5c0774a466dc535f2a1fba3411bd15b8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50530253"
---
# <a name="compiler-error-c2790"></a>Derleyici Hatası C2790

'super': Bu anahtar sözcük yalnızca sınıf üye işlevinin gövdesi içinde kullanılabilir

Bu hata iletisi görünür kullanıcı hiç olmadığı kadar çalışırsa kullanan anahtar sözcüğü [Süper](../../cpp/super.md) bir üye işlevin bağlamı dışında.

Aşağıdaki örnek, C2790 oluşturur:

```
// C2790.cpp
void f() {
   __super::g();   // C2790
}
```