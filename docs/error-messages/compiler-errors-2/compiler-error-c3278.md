---
title: "Derleyici Hatası C3278 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3278
dev_langs: C++
helpviewer_keywords: C3278
ms.assetid: 56f818f5-85a6-4792-843b-54fe16327658
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: ee3c14e1b6d306807735f8d58570089f128a1c19
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3278"></a>Derleyici Hatası C3278
doğrudan çağrı arabirimi veya saf yöntemi 'yöntemi' çalışma zamanında başarısız olur  
  
 Bir arabirim yöntemini veya izin saf bir yöntemle bir çağrı yapıldı.  
  
 Aşağıdaki örnek C3278 oluşturur:  
  
```  
// C3278_2.cpp  
// compile with: /clr  
using namespace System;  
interface class I  
{  
   void vmf();  
};  
  
public ref class C: public I  
{  
public:  
   void vmf()  
   {  
      Console::WriteLine( "In C::vmf()" );  
      I::vmf(); // C3278  
   }  
  
};  
  
int main()  
{  
   C^ pC = gcnew C;  
   pC->vmf();  
}  
```