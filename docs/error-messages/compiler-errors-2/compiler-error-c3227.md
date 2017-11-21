---
title: "Derleyici Hatası C3227 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3227
dev_langs: C++
helpviewer_keywords: C3227
ms.assetid: 7939c23a-96c8-43c2-89e9-f217d132d155
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 2f65791d709b5790144cd919bf06b61fd94da973
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3227"></a>Derleyici Hatası C3227
'parametresi': 'anahtar sözcüğü' genel tür ayırmak için kullanılamaz  
  
 Bir türü örneği için uygun bir oluşturucu gereklidir. Ancak, derleyici uygun bir oluşturucu kullanılabilir olduğundan emin olmak mümkün değildir.  
  
 Bu hatayı gidermek için genel türler yerine şablonları kullanabilirsiniz veya türünün bir örneğini oluşturmak için birkaç yöntemden birini kullanabilirsiniz.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C3227 oluşturur.  
  
```  
// C3227.cpp  
// compile with: /clr /c  
generic<class T> interface class ICreate {  
   static T Create();  
};  
  
generic <class T>  
where T : ICreate<T>  
ref class C {  
   void f() {  
      T t = new T;   // C3227  
  
      // OK  
      T t2 = ICreate<T>::Create();  
      T t3 = safe_cast<T>( System::Activator::CreateInstance(T::typeid) );  
   }  
};  
```