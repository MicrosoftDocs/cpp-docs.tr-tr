---
title: "Derleyici Hatası C2534 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2534
dev_langs: C++
helpviewer_keywords: C2534
ms.assetid: 481f9f54-5b51-4aa0-8eea-218f10807705
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: ee5b0e009833ca4f67f87bb234881b044215d5f0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2534"></a>Derleyici Hatası C2534
'tanımlayıcısı': Oluşturucusu bir değer döndüremiyor  
  
 Oluşturucu bir değer döndürür veya bir dönüş türüne sahip (değil bile bir `void` dönüş türü).  
  
 Bu hata, kaldırarak düzeltilebilir `return` Oluşturucusu tanımından deyimi.  
  
 Aşağıdaki örnek C2534 oluşturur:  
  
```  
// C2534.cpp  
class A {  
public:  
   int i;  
   A() { return i; }   // C2534  
};  
```