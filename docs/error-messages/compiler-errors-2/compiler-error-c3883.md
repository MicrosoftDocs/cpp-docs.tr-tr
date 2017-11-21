---
title: "Derleyici Hatası C3883 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3883
dev_langs: C++
helpviewer_keywords: C3883
ms.assetid: cdd1c1f4-f268-4469-9c62-d52303114b0c
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: ef1203b3162aa08f1de9a5a4ee68277d2c3489cc
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3883"></a>Derleyici Hatası C3883
'var': initonly statik veri üyesi başlatılması gerekir  
  
 Bir değişken olarak [initonly](../../dotnet/initonly-cpp-cli.md) düzgün başlatılmadı.  
  
 Aşağıdaki örnek C3883 oluşturur:  
  
```  
// C3883.cpp  
// compile with: /clr  
ref struct Y1 {  
   initonly  
   static int staticConst1;   // C3883  
};  
```  
  
 Aşağıdaki örnek, olası bir çözüm gösterilmektedir:  
  
```  
// C3883b.cpp  
// compile with: /clr /c  
ref struct Y1 {  
   initonly  
   static int staticConst2 = 0;  
};  
```  
  
 Aşağıdaki örnek, statik bir oluşturucu başlatılamadı gösterilmektedir:  
  
```  
// C3883c.cpp  
// compile with: /clr /LD  
ref struct Y1 {  
   initonly  
   static int staticConst1;  
  
   static Y1() {  
      staticConst1 = 0;  
   }  
};  
```