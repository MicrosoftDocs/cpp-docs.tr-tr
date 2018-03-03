---
title: "Derleyici Uyarısı (düzey 1) C4674 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4674
dev_langs:
- C++
helpviewer_keywords:
- C4674
ms.assetid: 638dae0b-b82c-4865-9599-72630827ca09
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3a9776af9dd17c747edb5ca54db197425613673e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4674"></a>Derleyici Uyarısı (düzey 1) C4674
'yöntemi' 'static' olarak bildirilmelidir ve tam olarak bir parametreye sahip  
  
Bir dönüşüm işleci imza doğru değildi. Kullanıcı tanımlı bir dönüştürme yöntemi olarak kabul edilmez. İşleçler tanımlama hakkında daha fazla bilgi için bkz: [kullanıcı tanımlı işleçler (C + +/ CLI)](../../dotnet/user-defined-operators-cpp-cli.md) ve [kullanıcı tanımlı Dönüşümler (C + +/ CLI)](../../dotnet/user-defined-conversions-cpp-cli.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C4674 oluşturur.  
  
```  
// C4674.cpp  
// compile with: /clr /WX /W1 /LD  
ref class G {  
   int op_Implicit(int i) {   // C4674  
      return 0;  
   }  
};  
```  
