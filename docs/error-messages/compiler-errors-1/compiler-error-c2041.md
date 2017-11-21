---
title: "Derleyici Hatası C2041 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2041
dev_langs: C++
helpviewer_keywords: C2041
ms.assetid: c9a33bb1-f9cf-47d6-bd21-7d867a8c37d5
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 4102f95b5a48860cba2e9ec79d2d5c22cd1413cf
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2041"></a>Derleyici Hatası C2041
Geçersiz sayı temel 'numara' için ' character'  
  
 Belirtilen karakter tabanı (örneğin, sekizli veya onaltılı) için geçerli bir sayı değil.  
  
 Aşağıdaki örnek C2041 oluşturur:  
  
```  
// C2041.cpp  
int i = 081;   // C2041  8 is not a base 8 digit  
```  
  
 Olası çözüm:  
  
```  
// C2041b.cpp  
// compile with: /c  
int j = 071;  
```