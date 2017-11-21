---
title: "Derleyici Hatası C2158 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2158
dev_langs: C++
helpviewer_keywords: C2158
ms.assetid: 39028899-e95c-4809-8e65-6111118641ee
caps.latest.revision: "4"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 84241663685ab1d12581b84bc761dcff77420fd2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2158"></a>Derleyici Hatası C2158
'type': #pragma make_public yönergesi yalnızca yerel şablon olmayan türleri şu anda desteklenmiyor  
  
 [Make_public](../../preprocessor/make-public.md) pragma yalnızca yerel, şablon olmayan türü için uygulanabilir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C2158 oluşturur.  
  
```  
// C2158.cpp  
// compile with: /clr /c  
ref class A {};  
#pragma make_public(A)   // C2158  
  
template< typename T >  
class B {};  
#pragma make_public(B)   // C2158  
#pragma make_public(B<int>)   // C2158  
  
void C () {}  
#pragma make_public(C)   // C2158  
  
class D {};  
#pragma make_public(D)   // OK  
```