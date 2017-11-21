---
title: "Derleyici Uyarısı (düzey 1) C4183 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4183
dev_langs: C++
helpviewer_keywords: C4183
ms.assetid: dc48312c-4b34-44dd-80ff-eb5f11d5ca47
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 025509de5f2b3dd14d957422042d8094d137924f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4183"></a>Derleyici Uyarısı (düzey 1) C4183
'tanımlayıcısı': dönüş türü; eksik üye işlevi 'int' döndürme varsayılır  
  
 Satır içi tanımı bir sınıf ya da bir yapı üye işlevi bir dönüş türüne sahip değil. Bu üye işlevi dönüş türü varsayılan olduğu varsayılır `int`.  
  
 Aşağıdaki örnek C4183 oluşturur:  
  
```  
// C4183.cpp  
// compile with: /W1 /c  
#pragma warning(disable : 4430)  
class MyClass1;  
class MyClass2 {  
   MyClass1() {};   // C4183  
};  
```