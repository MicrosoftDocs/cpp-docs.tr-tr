---
title: "Derleyici Hatası C3609 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3609
dev_langs: C++
helpviewer_keywords: C3609
ms.assetid: 801e7f79-4ac6-4f8f-955f-703cdf095d00
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: eb5d5127020ad1855c3fe7d94c362deeee53ccad
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3609"></a>Derleyici Hatası C3609
'member': korumalı veya son bir işlev sanal olmalıdır  
  
 [Korumalı](../../windows/sealed-cpp-component-extensions.md) ve [son](../../cpp/final-specifier.md) anahtar sözcükler yalnızca bir sınıf, yapı veya üye işlevi işaretlenmiş izin `virtual`.  
  
 Aşağıdaki örnek C3609 oluşturur:  
  
```  
// C3609.cpp  
// compile with: /clr /c  
ref class C {  
   int f() sealed;   // C3609  
   virtual int f2() sealed;   // OK  
};  
```  
