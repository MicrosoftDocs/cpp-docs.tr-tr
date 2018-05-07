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
ms.openlocfilehash: 2ca4af4e7353595dc687b77fa87acf70861bcb6f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-4-c4456"></a>Derleyici Uyarısı (düzey 4) C4456
  
> bildirimi '*tanımlayıcısı*' önceki yerel bildirimi gizler
  
Bildirimi *tanımlayıcısı* yerel kapsamda aynı ada sahip önceki yerel bildirimi bildirimi gizler. Bu uyarı, başvuran için bilmenizi sağlar *tanımlayıcısı* yerel kapsamında olabilir veya maksadınızı olmayabilir değil önceki yerel, yerel olarak bildirilen sürüme çözümleyin. Bu sorunu gidermek için yerel değişkenleri çakışmasını yerel diğer adları adlarıyla size öneririz.  
    
## <a name="example"></a>Örnek
  
Döngü denetlemek için değişken aşağıdaki örnek C4456 oluşturur `int x` ve yerel değişken `double x` içinde `member_fn` aynı ada sahip. Bu sorunu gidermek için yerel değişkenleri için farklı adlar kullanın.  
  
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
