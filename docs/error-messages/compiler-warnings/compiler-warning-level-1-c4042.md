---
title: Derleyici Uyarısı (düzey 1) C4042 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4042
dev_langs:
- C++
helpviewer_keywords:
- C4042
ms.assetid: e4bd861b-1194-426b-bf79-68c5b021eb0a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bcc4123c18eb9765841a5f6b54446cd064407700
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33278391"
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