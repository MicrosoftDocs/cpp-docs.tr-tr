---
title: "Derleyici Hatası C3768 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3768
dev_langs: C++
helpviewer_keywords: C3768
ms.assetid: 091f0d53-1dff-43fd-813d-5c43c85b6ab0
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ba2f52622cde34a8301529d569790c67a72bbb74
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3768"></a>Derleyici Hatası C3768
bir sanal vararg işlev adresi saf yönetilen kodda alamıyor  
  
 **/CLR: pure** derleyici seçeneği Visual Studio 2015'te kullanım dışıdır.  
  
 İle derleme yapılırken `/clr:pure`, bir sanal adresini alamıyor `vararg` işlevi.  
  
## <a name="example"></a>Örnek  

 Aşağıdaki örnek C3768 oluşturur:  
  
```  
// C3768.cpp  
// compile with: /clr:pure  
struct A  
{  
   virtual void f(...);  
};  
  
int main()  
{  
   &(A::f);   // C3768  
}  
```