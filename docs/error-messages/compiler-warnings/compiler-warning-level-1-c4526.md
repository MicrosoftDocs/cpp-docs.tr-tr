---
title: "Derleyici Uyarısı (düzey 1) C4526 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4526
dev_langs: C++
helpviewer_keywords: C4526
ms.assetid: 490f8916-5fdc-4cad-b412-76c3382a5976
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 00ffa9e20781d8d5d1405d6bf5546b47a6530b88
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4526"></a>Derleyici Uyarısı (düzey 1) C4526
'function': statik üye işlevi sanal işlevi geçersiz kılma olamaz ' yoksayıldı sanal function'override sanal işlev gizli  
  
 Statik üye fonksiyonu hem sanal hem de statik üye fonksiyonu yapar sanal işlevi geçersiz kılmak için ölçütlerine.  
  
 Aşağıdaki kod C4526 oluşturur:  
  
```  
// C4526.cpp  
// compile with: /W1 /c  
// C4526 expected  
struct myStruct1 {  
   virtual void __stdcall func( int ) = 0;  
};  
  
struct myStruct2: public myStruct1 {  
   static void __stdcall func( int );  
};  
```  
  
 Olası düzeltmeler şunlardır:  
  
-   Taban sınıf sanal işlevi geçersiz kılmak için işlevi amaçlanıyorsa, statik belirteci kaldırın.  
  
-   Statik üye işlevi işlevi amaçlanıyorsa, temel sınıf sanal işlev çakışan olmayan şekilde yeniden adlandırın.