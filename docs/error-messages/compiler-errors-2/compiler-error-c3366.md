---
title: "Derleyici Hatası C3366 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3366
dev_langs: C++
helpviewer_keywords: C3366
ms.assetid: efc55bcf-c16d-43c1-a36f-87a6165fa2a8
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: b862e606b86eca0a7eb7f2ad1e91f2776c8c0b23
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3366"></a>Derleyici Hatası C3366
'değişkeni': statik veri üyeleri yönetilen veya WinRTtypes sınıf tanımı içinde tanımlanması gerekir  
  
 Statik bir üyenin WinRT ya da .NET sınıf ya da bu sınıf veya arabirim tanımı dışında arabirimi başvuru göndermeye çalıştı.  
  
 Derleyici (meta verileri sonra tek seferde yaymak üzere) sınıfının tam tanımını bilmesi gerekir ve içinde sınıf başlatılması statik veri üyeleri gerektirir.  
  
 Örneğin, aşağıdaki örnek C3366 oluşturur ve düzeltmek gösterilmektedir:  
  
```  
// C3366.cpp  
// compile with: /clr /c  
ref class X {  
   public:  
   static int i;   // initialize i here to avoid C3366  
};  
  
int X::i = 5;      // C3366  
```  
