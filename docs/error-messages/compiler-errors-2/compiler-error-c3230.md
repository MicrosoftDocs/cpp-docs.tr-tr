---
title: "Derleyici Hatası C3230 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3230
dev_langs: C++
helpviewer_keywords: C3230
ms.assetid: 5ec53f25-59f6-4801-81e7-7b68bf04994d
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 76cd091e910015b2d6df8bd476f40f663c9f681b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3230"></a>Derleyici Hatası C3230
'function': 'template' için şablon tür bağımsız değişkeni bir genel tür parametresi içeremez: 'param'  
  
 Şablonları derleme zamanında örneği, ancak genel türler çalışma zamanında örneği. Bu nedenle, şablon zaman genel tür son bilinen çalışma zamanında başlatılamaz olduğundan, şablon çağırabilirsiniz genel kod oluşturmak mümkün değil.  
  
 Aşağıdaki örnek C3230 oluşturur:  
  
```  
// C3230.cpp  
// compile with: /clr /LD  
template <class S>   
void f(S t);  
  
generic <class U>  
ref class C {  
   void f1(U x) {  
      f(x);   // C3230  
   }  
};  
```