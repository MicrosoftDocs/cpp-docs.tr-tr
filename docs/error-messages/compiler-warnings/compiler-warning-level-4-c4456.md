---
title: Derleyici Uyarısı (düzey 4) C4456 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4456
dev_langs:
- C++
helpviewer_keywords:
- C4456
ms.assetid: 5ab39fc1-0e19-461b-842b-4da80560b044
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9ab6939fe37260b906a43c4e2ff6683733348952
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46039900"
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
