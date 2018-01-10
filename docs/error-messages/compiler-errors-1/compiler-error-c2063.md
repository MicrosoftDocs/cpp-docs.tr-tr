---
title: "Derleyici Hatası C2063 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2063
dev_langs: C++
helpviewer_keywords: C2063
ms.assetid: 0a90c18f-4029-416a-9128-e8713b53e6f1
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 544e61d19fc9f00e37df51666fdc0f98bbb84e5f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2063"></a>Derleyici Hatası C2063
'tanımlayıcısı': bir işlev değil  
  
 Tanımlayıcı bir işlevi olarak kullanılan ancak bir işlevi olarak bildirilmedi.  
  
 Aşağıdaki örnek C2063 oluşturur:  
  
```  
// C2063.c  
int main() {  
   int i, j;  
   j = i();    // C2063, i is not a function  
}  
```  
  
 Olası çözüm:  
  
```  
// C2063b.c  
int i() { return 0;}  
int main() {  
   int j;  
   j = i();  
}  
```