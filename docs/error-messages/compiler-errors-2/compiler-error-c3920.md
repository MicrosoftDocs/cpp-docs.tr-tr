---
title: "Derleyici Hatası C3920 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3920
dev_langs: C++
helpviewer_keywords: C3920
ms.assetid: 66e91f28-ed82-4ce2-bf22-c0c74905b1ed
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 2e2bf82de4e32c2b0ae586c78c69ce474947c3ec
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3920"></a>Derleyici Hatası C3920
' işleci '': bir sonek artırma/azaltma WinRT veya CLR işleci sonek arama tanımlayamazsınız WinRT veya CLR işleci karşılık gelen önek çağıracaktır WinRT veya CLR işleci (op_Increment/op_Decrement), ancak sonek semantiği ile  
  
 Windows çalışma zamanı ve CLR sonek işleci desteklemez ve kullanıcı tanımlı sonek işleçleri izin verilmez.  Bir önek işleci tanımlama ve önek işleci öncesi ve sonrası artışı işlemleri için kullanılır.  
  
 Aşağıdaki örnek C3920 oluşturur ve düzeltmek gösterilmektedir:  
  
```  
// C3920.cpp  
// compile with: /clr /LD  
public value struct V {  
   static V operator ++(V me, int)  
   // try the following line instead  
   // static V operator ++(V me)  
   {   // C3920  
      me.m_i++;  
      return me;  
   }  
  
   int m_i;  
};  
  
```