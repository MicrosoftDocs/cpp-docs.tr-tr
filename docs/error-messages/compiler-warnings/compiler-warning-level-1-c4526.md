---
title: Derleyici Uyarısı (düzey 1) C4526 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4526
dev_langs:
- C++
helpviewer_keywords:
- C4526
ms.assetid: 490f8916-5fdc-4cad-b412-76c3382a5976
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c5a38d629d61e16b038701522d4bb27a4de7391d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
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