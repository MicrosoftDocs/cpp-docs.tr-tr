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
ms.openlocfilehash: 815433004756e4726ee4e562cbd0e424a35d377a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33292977"
---
# <a name="compiler-warning-level-4-c4458"></a>Derleyici Uyarısı (düzey 4) C4458
  
> bildirimi '*tanımlayıcısı*' gizler üye sınıfı
  
Bildirimi *tanımlayıcısı* yerel kapsamda aynı adlı bildirimi gizler *tanımlayıcısı* sınıfı kapsamda. Bu uyarı, başvuran için bilmenizi sağlar *tanımlayıcısı* bu kapsamda olabilir veya maksadınızı olmayabilir sınıf üyesi sürümünü değil, yerel olarak bildirilen sürüme çözümleyin. Bu sorunu gidermek için yerel değişkenleri çakışmasını sınıf üye adlarının adlarıyla size öneririz.  
    
## <a name="example"></a>Örnek
  
Aşağıdaki örnek C4458 oluşturur çünkü parametresi `x` ve yerel değişken `y` içinde `member_fn` sınıfında veri üye olarak aynı ada sahip. Bu sorunu gidermek için yerel değişkenleri ve parametreleri için farklı adlar kullanın.  
  
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
