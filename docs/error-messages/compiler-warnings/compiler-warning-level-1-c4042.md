---
title: "Derleyici Uyarısı (düzey 1) C4042 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4042
dev_langs: C++
helpviewer_keywords: C4042
ms.assetid: e4bd861b-1194-426b-bf79-68c5b021eb0a
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 3369b2786c552e408e8eedf8e6ed8bf73f272ff6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4042"></a>Derleyici Uyarısı (düzey 1) C4042
'tanımlayıcısı': hatalı depolama sınıfı var.  
  
 Belirtilen depolama sınıfı, şu tanımlayıcıyla bu bağlamda kullanılamaz. Derleyici yerine varsayılan depolama sınıfı kullanır:  
  
-   `extern`, varsa *tanımlayıcısı* bir işlevdir.  
  
-   **Otomatik**, *tanımlayıcısı* biçimsel parametresi ya da yerel değişken.  
  
-   Depolama sınıfı, varsa *tanımlayıcısı* genel bir değişkendir.  
  
 Bu uyarı dışındaki bir depolama sınıfı belirterek kaynaklanabilir **kaydetmek** parametre bildirimi.  
  
 Aşağıdaki örnek C4042 oluşturur  
  
```  
// C4042.cpp  
// compile with: /W1 /LD  
int func2( __declspec( thread ) int tls_i )    // C4042  
// try the following line instead  
// int func2( int tls_i )  
{  
   return tls_i;  
}  
```