---
title: "Derleyici Hatası C3413 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3413
dev_langs: C++
helpviewer_keywords: C3413
ms.assetid: de6c9b05-c373-4bd8-8cb0-12c2cd2e5674
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 1403c65b0eac3879cbbcd612b077d4b4b3937b49
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3413"></a>Derleyici Hatası C3413
'name': Geçersiz açık örnekleme  
  
 Derleyici hatalı oluşturulmuş bir açık örnekleme algıladı.  
  
 Aşağıdaki örnek C3413 oluşturur:  
  
```  
// C3413.cpp  
template  
class MyClass {};   // C3413  
```  
  
 Olası çözüm:  
  
```  
// C3413b.cpp  
// compile with: /c  
template <class T>  
class MyClass {};  
  
template <>  
class MyClass<int> {};  
```