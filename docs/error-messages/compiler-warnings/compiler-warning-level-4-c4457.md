---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 4) C4457'
title: Derleyici Uyarısı (düzey 4) C4457
ms.date: 11/04/2016
f1_keywords:
- C4457
helpviewer_keywords:
- C4457
ms.assetid: 02fd149a-917d-4f67-97a6-eb714572271f
ms.openlocfilehash: 8898189668eba95619e6bd0d0ccf1cb8ca3afdfe
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97251420"
---
# <a name="compiler-warning-level-4-c4457"></a>Derleyici Uyarısı (düzey 4) C4457

> '*Identifier*' bildirimi işlev parametresini gizliyor

Yerel kapsamdaki *tanımlayıcının* bildirimi, özdeş olarak adlandırılmış işlev parametresinin bildirimini gizler. Bu uyarı, yerel kapsamdaki *tanımlayıcıya* yapılan başvuruların parametre değil, yerel olarak belirtilen sürüme çözümlendiğine, ancak sizin amacınızı belirleyebilmenizi sağlar. Bu sorunu onarmak için, parametre adlarıyla çakışmayan yerel değişken adları vermenizi öneririz.

## <a name="example"></a>Örnek

Aşağıdaki örnek, `x` içindeki parametresi ve yerel değişkeni `x` `member_fn` aynı ada sahip olduğundan C4457 oluşturur. Bu sorunu onarmak için, parametreler ve yerel değişkenler için farklı adlar kullanın.

```cpp
// C4457_hide.cpp
// compile with: cl /W4 /c C4457_hide.cpp

struct S {
    void member_fn(unsigned x) {
        double a = 0;
        for (int x = 0; x < 10; ++x) {  // C4457
            a += x; // uses local x
        }
        a += x; // uses parameter x
    }
} s;
```
