---
title: "Derleyici Hatası C3887 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3887
dev_langs: C++
helpviewer_keywords: C3887
ms.assetid: a7e82426-ef99-437b-9562-2822004e18fe
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 7dccbd3a34764eedc53c69ddd69c693cc4782d2a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3887"></a>Derleyici Hatası C3887
'var': Başlatıcı değişmez değer veri üyesi için sabit bir ifade olmalıdır  
  
 A [değişmez değer](../../windows/literal-cpp-component-extensions.md) veri üyesi ile sabit bir ifade yalnızca başlatılabilir.  
  
 Aşağıdaki örnek C3887 oluşturur:  
  
```  
// C3887.cpp  
// compile with: /clr  
ref struct Y1 {  
   static int i = 9;  
   literal  
   int staticConst = i;   // C3887  
};  
```  
  
 Olası çözüm:  
  
```  
// C3887b.cpp  
// compile with: /clr /c  
ref struct Y1 {  
   literal  
   int staticConst = 9;  
};  
```