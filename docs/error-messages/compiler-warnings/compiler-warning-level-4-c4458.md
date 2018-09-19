---
title: Derleyici Uyarısı (düzey 4) C4458 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4458
dev_langs:
- C++
helpviewer_keywords:
- C4458
ms.assetid: 7bdaa1b1-0caf-4d68-98c4-6bdd441c23fb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 873aa94db899ae6620e2bbb1f24277c6e7c841c4
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46094552"
---
# <a name="compiler-warning-level-4-c4458"></a>Derleyici Uyarısı (düzey 4) C4458

> bildirimi '*tanımlayıcı*' sınıf üyesini gizliyor

Bildirimi *tanımlayıcı* yerel kapsamda aynı adlı bildirimi gizler *tanımlayıcı* sınıf kapsamında. Bu uyarı, başvuruları size sağlar *tanımlayıcı* bu kapsamda amacınızla olmayabilir veya sınıf üyesi sürümünü değil, yerel olarak bildirilen sürümüne çözün. Bu sorunu çözmek için yerel değişkenler çakışmasını sınıf üye adları adlarla size öneririz.

## <a name="example"></a>Örnek

Aşağıdaki örnek C4458 oluşturur çünkü parametre `x` ve yerel değişkeni `y` içinde `member_fn` sınıf veri üyeleri olarak aynı ada sahip. Bu sorunu gidermek için yerel değişkenleri ve parametreleri için farklı adlar kullanın.

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
