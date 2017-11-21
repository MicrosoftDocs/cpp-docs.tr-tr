---
title: "Derleyici Uyarısı (düzey 4) C4061 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4061
dev_langs: C++
helpviewer_keywords: C4061
ms.assetid: a99cf88e-7941-4519-8b1b-f6889d914b2f
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: a24a3d1929184e02e03fd1609b2a5220a84fad0a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-4-c4061"></a>Derleyici Uyarısı (düzey 4) C4061
Numaralandırıcı 'tanıtıcısı' anahtarda enum 'numaralandırma' servis talebi etiket tarafından açıkça işlenmedi  
  
 Hiçbir ilişkili işleyici listeleme sahip bir `switch` deyimi.  
  
 Varsayılan olarak bu uyarı kapalıdır. Bkz: [derleyici uyarıları emin olduğunuz kapalı varsayılan](../../preprocessor/compiler-warnings-that-are-off-by-default.md) daha fazla bilgi için.  
  
 Aşağıdaki örnek C4061 oluşturur:  
  
```  
// C4061.cpp  
// compile with: /W4  
#pragma warning(default : 4061)  
  
enum E { a, b, c };  
void func ( E e )  
{  
   switch(e)  
   {  
      case a:  
      case b:  
      default:  
         break;  
   }   // C4061 c' not handled  
}  
  
int main()  
{  
}  
```