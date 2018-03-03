---
title: "Derleyici Hatası C3366 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3366
dev_langs:
- C++
helpviewer_keywords:
- C3366
ms.assetid: efc55bcf-c16d-43c1-a36f-87a6165fa2a8
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5d94d3a18c02cfe81f6c3ee96635c9388f54308d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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
