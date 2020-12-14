---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 4) C4458'
title: Derleyici Uyarısı (düzey 4) C4458
ms.date: 11/04/2016
f1_keywords:
- C4458
helpviewer_keywords:
- C4458
ms.assetid: 7bdaa1b1-0caf-4d68-98c4-6bdd441c23fb
ms.openlocfilehash: f631fe4086c69732c972161ae7bb6096232b2740
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97241267"
---
# <a name="compiler-warning-level-4-c4458"></a>Derleyici Uyarısı (düzey 4) C4458

> '*Identifier*' bildirimi sınıf üyesini gizliyor

Yerel kapsamdaki *tanımlayıcının* bildirimi, sınıf kapsamındaki özdeş olarak adlandırılmış *tanımlayıcının* bildirimini gizler. Bu uyarı, bu kapsamdaki *tanımlayıcıya* yapılan başvuruların, sınıf üyesi sürümü değil, yerel olarak belirtilen sürüme çözümlendiğine, sizin amacınızı etkileyebilecek veya bu olmayabilir. Bu sorunu onarmak için, sınıf üyesi adlarıyla çakışmayan yerel değişken adları vermenizi öneririz.

## <a name="example"></a>Örnek

`x`İçindeki parametresi ve yerel değişkeni, `y` `member_fn` sınıfındaki veri üyeleriyle aynı adlara sahip olduğundan aşağıdaki örnek C4458 oluşturur. Bu sorunu onarmak için, parametreler ve yerel değişkenler için farklı adlar kullanın.

```cpp
// C4458_hide.cpp
// compile with: cl /W4 /c C4458_hide.cpp

struct S {
    int x;
    float y;
    void member_fn(long x) {   // C4458
        double y;  // C4458
        y = x;
        // To fix this issue, change the parameter name x
        // and local name y to something that does not
        // conflict with the data member names.
    }
} s;
```
