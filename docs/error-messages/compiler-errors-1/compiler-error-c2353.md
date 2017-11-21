---
title: "Derleyici Hatası C2353 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2353
dev_langs: C++
helpviewer_keywords: C2353
ms.assetid: d57f8f77-d9b1-4bba-a940-87ec269ad183
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: a2bb8210a1b0d2eb2150e9916b1230180cb72420
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2353"></a>Derleyici Hatası C2353
özel durum belirtimine izin verilmez  
  
 Özel durum belirtimleri yönetilen sınıflar üye fonksiyonları izin verilmez.  
  
 Aşağıdaki örnek C2353 oluşturur:  
  
```  
// C2353.cpp  
// compile with: /clr /c  
ref class X {  
   void f() throw(int);   // C2353  
   void f();   // OK  
};  
```