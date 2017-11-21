---
title: "Derleyici Hatası C2574 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2574
dev_langs: C++
helpviewer_keywords: C2574
ms.assetid: 3e1c5c18-ee8b-4dbb-bfc0-d3b8991af71b
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 31e6b1c7dc2e2a1fcb0a04e284d0251e59ebb8bd
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2574"></a>Derleyici Hatası C2574
'yıkıcı': statik olarak bildirilemez  
  
 Yıkıcılar ne oluşturucular bildirilebilir `static`.  
  
 Aşağıdaki örnek C2574 oluşturur:  
  
```  
// C2574.cpp  
// compile with: /c  
class A {  
   virtual static ~A();   // C2574  
   //  try the following line instead  
   // virtual ~A();  
};  
```