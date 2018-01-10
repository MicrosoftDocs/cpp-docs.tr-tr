---
title: "Derleyici Uyarısı (düzey 4) C4456 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4456
dev_langs: C++
helpviewer_keywords: C4456
ms.assetid: 5ab39fc1-0e19-461b-842b-4da80560b044
caps.latest.revision: "0"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9e298f092f546c589606be42b6e7b9faed15ddd4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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
