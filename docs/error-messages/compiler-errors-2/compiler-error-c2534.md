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
ms.workload: cplusplus
ms.openlocfilehash: d16f4bcd88707585cd8215b2b512c37a29f82b81
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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