---
title: Derleyici Uyarısı (düzey 4) C4456
ms.date: 11/04/2016
f1_keywords:
- C4456
helpviewer_keywords:
- C4456
ms.assetid: 5ab39fc1-0e19-461b-842b-4da80560b044
ms.openlocfilehash: 006628721598d838070412c895f64b9a8d3de4e9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62391510"
---
# <a name="compiler-warning-level-4-c4456"></a>Derleyici Uyarısı (düzey 4) C4456

> bildirimi '*tanımlayıcı*' önceki yerel bildirimi gizliyor

Bildirimi *tanımlayıcı* yerel kapsama önceki yerel bildirimi aynı adlı bildirimi gizler. Bu uyarı, başvuruları size sağlar *tanımlayıcı* yerel kapsama amacınızla olmayabilir veya değil önceki yerel, yerel olarak bildirilen sürümüne çözün. Bu sorunu çözmek için yerel değişkenler çakışmasını diğer yerel adları adlarla size öneririz.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4456 oluşturur, döngüyü denetlemek çünkü değişken `int x` ve yerel değişkeni `double x` içinde `member_fn` aynı ada sahip. Bu sorunu çözmek için yerel değişkenler için farklı adlar kullanın.

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
