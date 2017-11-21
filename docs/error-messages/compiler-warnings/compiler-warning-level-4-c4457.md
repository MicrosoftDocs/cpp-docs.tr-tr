---
title: "Derleyici Uyarısı (düzey 4) C4457 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4457
dev_langs: C++
helpviewer_keywords: C4457
ms.assetid: 02fd149a-917d-4f67-97a6-eb714572271f
caps.latest.revision: "0"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: a8ede4500e579436d5d6b9db581a06c14a6aca43
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-4-c4457"></a>Derleyici Uyarısı (düzey 4) C4457
  
> bildirimi '*tanımlayıcısı*' gizler işlev parametresi
  
Bildirimi *tanımlayıcısı* yerel kapsamda aynı adlı işlev parametresi bildirimi gizler. Bu uyarı, başvuran için bilmenizi sağlar *tanımlayıcısı* yerel kapsamında değil veya maksadınızı olmayabilir parametresi, yerel olarak bildirilen sürüme çözümleyin. Bu sorunu gidermek için yerel değişkenleri çakışmasını parametre adları adlarıyla size öneririz.  
    
## <a name="example"></a>Örnek
  
Aşağıdaki örnek C4457 oluşturur çünkü parametresi `x` ve yerel değişken `x` içinde `member_fn` aynı ada sahip. Bu sorunu gidermek için yerel değişkenleri ve parametreleri için farklı adlar kullanın.  
  
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
