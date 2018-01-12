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
ms.workload: cplusplus
ms.openlocfilehash: e932f72f163ce8db62f506eaab921c4e91b24928
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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