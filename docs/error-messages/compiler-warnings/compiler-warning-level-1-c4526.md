---
title: "Derleyici Uyarısı (düzey 1) C4526 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4526
dev_langs:
- C++
helpviewer_keywords:
- C4526
ms.assetid: 490f8916-5fdc-4cad-b412-76c3382a5976
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a74d7d2e2c745a4c8e29736c1e3a7fc38892d5f6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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