---
title: Derleyici Hatası C3366 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3366
dev_langs:
- C++
helpviewer_keywords:
- C3366
ms.assetid: efc55bcf-c16d-43c1-a36f-87a6165fa2a8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c26bfbb5d66ad22484184bd361f14004ed8aa30c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33254280"
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
