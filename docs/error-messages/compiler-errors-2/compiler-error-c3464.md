---
title: "Derleyici Hatası C3464 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3464
dev_langs: C++
helpviewer_keywords: C3464
ms.assetid: 0ede05dc-4486-4921-8e8c-78ab5a2e09c5
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ff80d33e78bb90b1cd8f7d3e0703d4236df375d8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3464"></a>Derleyici Hatası C3464
'type' iç içe geçmiş tür iletilemez  
  
 Tür iletme iç içe geçmiş türler üzerinde çalışmaz.  
  
 Daha fazla bilgi için bkz: [tür iletme (C + +/ CLI)](../../windows/type-forwarding-cpp-cli.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bir bileşen oluşturur.  
  
```  
// C3464.cpp  
// compile with: /LD /clr  
public ref class R {  
public:  
   ref class N {};  
};  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C3464 oluşturur.  
  
```  
// C3464_b.cpp  
// compile with: /clr /c  
#using "C3464.dll"  
[assembly:TypeForwardedTo(R::N::typeid)];   // C3464  
[assembly:TypeForwardedTo(R::typeid)];   // OK  
```