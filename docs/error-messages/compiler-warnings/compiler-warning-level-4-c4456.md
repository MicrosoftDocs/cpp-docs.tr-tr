---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 4) C4456'
title: Derleyici Uyarısı (düzey 4) C4456
ms.date: 11/04/2016
f1_keywords:
- C4456
helpviewer_keywords:
- C4456
ms.assetid: 5ab39fc1-0e19-461b-842b-4da80560b044
ms.openlocfilehash: f066de07b0c6bf7a7b5de3143909e402b0fedde3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97241319"
---
# <a name="compiler-warning-level-4-c4456"></a>Derleyici Uyarısı (düzey 4) C4456

> '*Identifier*' bildirimi önceki yerel bildirimi gizliyor

Yerel kapsamdaki *tanımlayıcının* bildirimi, aynı ada sahip önceki yerel bildirimin bildirimini gizler. Bu uyarı, yerel kapsamdaki *tanımlayıcıya* yapılan başvuruların, önceki yerel olarak değil, yerel olarak belirtilen sürüme çözümlendiğine, ancak sizin amacınız anlamına gelir. Bu sorunu onarmak için, diğer yerel adlarla çakışmayan yerel değişken adlarına izin vermenizi öneririz.

## <a name="example"></a>Örnek

Aşağıdaki örnek, içindeki Loop denetim değişkeni `int x` ve yerel değişkeni `double x` `member_fn` aynı ada sahip olduğundan C4456 oluşturur. Bu sorunu onarmak için yerel değişkenler için farklı adlar kullanın.

```cpp
// C4456_hide.cpp
// compile with: cl /W4 /c C4456_hide.cpp

struct S {
    void member_fn(unsigned u) {
        double x = 0;
        for (int x = 0; x < 10; ++x) {  // C4456
            u += x; // uses local int x
        }
        x += u; // uses local double x
    }
} s;
```
