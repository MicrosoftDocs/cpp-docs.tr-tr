---
title: "Derleyici Hatası C2992 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2992
dev_langs: C++
helpviewer_keywords: C2992
ms.assetid: 01b16447-43fe-4e91-9a5a-af884a166a31
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 0d6bf275d4d2ba42168112547832c5b7e0d7c62f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2992"></a>Derleyici Hatası C2992
'class': eksik veya geçersiz tür parametresi listesi  
  
 Sınıf öncesinde bir `template` veya **genel** anahtar sözcüğüyle parametreler eksik veya geçersiz.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C2992 oluşturur:  
  
```  
// C2992.cpp  
// compile with: /c  
template <class T>   
struct TC1 {  
   template <class U>  
   struct TC2;  
};  
  
template <class T>   struct TC1<T>::TC2 {};   // C2992  
  
// OK  
template <class T>  
template <class U>  
struct TC1<T>::TC2 {};  
 // C2992 can also occur when using generics:  
// C2992c.cpp  
// compile with: /clr /c  
generic <class T>  
ref struct GC1 {  
   generic <class U>  
   ref struct GC2;  
};  
  
generic <class T> ref struct GC1<T>::GC2 {};   // C2992  
  
// OK  
generic <class T>  
generic <class U>  
ref struct GC1<T>::GC2 {};  
```