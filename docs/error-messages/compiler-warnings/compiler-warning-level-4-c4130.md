---
title: "Derleyici Uyarısı (düzey 4) C4130 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4130
dev_langs:
- C++
helpviewer_keywords:
- C4130
ms.assetid: 45e4c7b2-6b51-41c7-ba5e-941aa5c7d3dc
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 282f9755470baca115d0595b002b929874619a93
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4130"></a>Derleyici Uyarısı (düzey 4) C4130
'işleci': mantıksal işlemi adresi dize sabiti  
  
 Bir dize sabit değeri adresiyle işlecini kullanarak beklenmeyen kod oluşturur.  
  
 Aşağıdaki örnek C4130 oluşturur:  
  
```  
// C4130.cpp  
// compile with: /W4  
int main()  
{  
   char *pc;  
   pc = "Hello";  
   if (pc == "Hello") // C4130  
   {  
   }  
}  
```  
  
 **Varsa** deyimi işaretçinin depolanan değerle karşılaştırır `pc` "Hello" dizesini adresine hangi ayrılır ayrı olarak dize kodunda her defasında. **Varsa** deyimi gösterdiği dize karşılaştırma değil `pc` "Hello" dizesiyle.  
  
 Dizeleri karşılaştırmak için kullanmak `strcmp` işlevi.