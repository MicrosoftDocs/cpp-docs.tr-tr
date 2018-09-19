---
title: Derleyici Uyarısı (düzey 4) C4457 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4457
dev_langs:
- C++
helpviewer_keywords:
- C4457
ms.assetid: 02fd149a-917d-4f67-97a6-eb714572271f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 62232a814bed47f8b6a5041d20e6f37776abffe8
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46093538"
---
# <a name="compiler-warning-level-4-c4457"></a>Derleyici Uyarısı (düzey 4) C4457

> bildirimi '*tanımlayıcı*' işlev parametresini gizliyor

Bildirimi *tanımlayıcı* yerel kapsamda aynı adlı işlevi parametre bildirimi gizler. Bu uyarı, başvuruları size sağlar *tanımlayıcı* yerel kapsamda değil amacınızla olmayabilir veya parametre, yerel olarak bildirilen sürümüne çözün. Bu sorunu çözmek için yerel değişkenler çakışmasını parametre adları adlarla size öneririz.

## <a name="example"></a>Örnek

Aşağıdaki örnek C4457 oluşturur çünkü parametre `x` ve yerel değişkeni `x` içinde `member_fn` aynı ada sahip. Bu sorunu gidermek için yerel değişkenleri ve parametreleri için farklı adlar kullanın.

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
