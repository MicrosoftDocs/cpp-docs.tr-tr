---
title: Derleyici Uyarısı (düzey 4) C4130 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4130
dev_langs:
- C++
helpviewer_keywords:
- C4130
ms.assetid: 45e4c7b2-6b51-41c7-ba5e-941aa5c7d3dc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 226b715689e506cb34ea6e7684f9ddcf041e638b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
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