---
title: "Derleyici Uyarısı (düzey 1) C4812 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4812
dev_langs: C++
helpviewer_keywords: C4812
ms.assetid: a7f5721f-2019-44de-ad62-ed30bac8b1f3
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: a7dff9fec76cfc000216335840058241e11dfab3
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4812"></a>Derleyici Uyarısı (düzey 1) C4812
eski bildirim stili: Lütfen bunun yerine 'new_syntax' kullanın  
  
 Visual C++ geçerli sürümde, açık Oluşturucu uzmanlık hala desteklenmektedir, ancak gelecekteki bir sürümde desteklenmeyebilir.  
  
 Aşağıdaki örnek C4812 oluşturur:  
  
```  
// C4812.cpp  
// compile with: /W1 /c  
template <class T>   
class MyClass;  
  
template<class T>  
class MyClass<T*> {  
   MyClass();  
};  
  
template<class T>  
MyClass<T*>::MyClass<T*>() {}   // C4812  
// try the following line instead  
// MyClass<T*>::MyClass() {}  
```