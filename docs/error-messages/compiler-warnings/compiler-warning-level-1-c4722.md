---
title: "Derleyici Uyarısı (düzey 1) C4722 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4722
dev_langs: C++
helpviewer_keywords: C4722
ms.assetid: d8660710-f67b-4f59-a5fd-59259475529e
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 8616fe9834b0f73445bbcb8ffea4d35af3895b12
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4722"></a>Derleyici Uyarısı (düzey 1) C4722
'function': yıkıcı hiçbir zaman döndürür, olası bellek sızıntısı  
  
 Denetim akışı bir yıkıcı sonlandırır. İş parçacığı veya tüm programı sonlandırır ve ayrılan kaynakları serbest.  Ayrıca, özel durum işleme sırasında yığını geriye doğru izleme için bir yıkıcı çağrılacağı, yürütülebilir davranışını tanımlanmamıştır.  
  
 Çözümlemek için değil döndürülecek yıkıcı neden işlev çağrısı kaldırın.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C4722 oluşturur:  
  
```  
// C4722.cpp  
// compile with: /O1 /W1 /c  
#include <stdlib.h>  
class C {  
public:  
   C();  
   ~C() { exit(1); };   // C4722  
};  
  
extern void func (C*);  
  
void Test(){  
   C x;  
   func(&x);  
   // control will not leave Test because destructor will exit  
}  
```