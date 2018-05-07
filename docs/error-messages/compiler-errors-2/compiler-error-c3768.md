---
title: Derleyici Hatası C3768 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3768
dev_langs:
- C++
helpviewer_keywords:
- C3768
ms.assetid: 091f0d53-1dff-43fd-813d-5c43c85b6ab0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3634ecf3eb1417095cce144706838113b5ad2a0e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
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