---
title: "Derleyici Hatası C2917 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2917
dev_langs: C++
helpviewer_keywords: C2917
ms.assetid: ec9da9ee-0f37-47b3-87dd-19ef5a14dc4c
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: b66aee3abc57f7505f829fcedffdf2ffd927d839
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2917"></a>Derleyici Hatası C2917
'name': Geçersiz şablon parametresi  
  
 Şablon parametresi değildi bir tanımlayıcı şablon parametre listesini içerir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C2917 oluşturur.  
  
```  
// C2917.cpp  
// compile with: /c  
template<class T> class Vector {  
   void sort();  
};  
  
template<class T*> void Vector<T>::sort() {}   // C2917  
// try the following line instead  
// template<class T> void Vector<T>::sort() {}  
```