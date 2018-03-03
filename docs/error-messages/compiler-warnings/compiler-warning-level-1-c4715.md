---
title: "Derleyici Uyarısı (düzey 1) C4715 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4715
dev_langs:
- C++
helpviewer_keywords:
- C4715
ms.assetid: 1c819bf7-0d8b-4f5e-b338-9cc292870439
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2b060585cd3ba6b51c9c91d42e5f3fecaf74ae1b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4715"></a>Derleyici Uyarısı (düzey 1) C4715
'function': değer tüm denetim yollarına döndürme  
  
 Belirtilen işlev, bir değer döndürmesi olası değil.  
  
## <a name="example"></a>Örnek  
  
```  
// C4715a.cpp  
// compile with: /W1 /LD  
int func1( int i )  
{  
   if( i )  
   return 3;  // C4715 warning, nothing returned if i == 0  
}  
```  
  
 Bu uyarı önlemek için tüm yolları işlev için dönüş değeri atamak böylece kodu değiştirin:  
  
```  
// C4715b.cpp  
// compile with: /LD  
int func1( int i )  
{  
   if( i ) return 3;  
   else return 0;     // OK, always returns a value  
}  
```  
  
 Kodunuzu hiçbir zaman döndüren, aşağıdaki örnekte olduğu gibi bir işlev çağrısı içerebilir mümkündür:  
  
```  
// C4715c.cpp  
// compile with: /W1 /LD  
void fatal()  
{  
}  
int glue()  
{  
   if(0)  
      return 1;  
   else if(0)  
      return 0;  
   else  
      fatal();   // C4715  
}  
```  
  
 Bu kod derleyici, bilmediğinden, aynı zamanda bir uyarı oluşturur `fatal` hiçbir zaman döndürür. Bu kod hata iletisine oluşturma önlemek için bildirme `fatal` kullanarak [__declspec(noreturn)](../../cpp/noreturn.md).