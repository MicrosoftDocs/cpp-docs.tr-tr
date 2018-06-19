---
title: Derleyici Hatası C2436 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2436
dev_langs:
- C++
helpviewer_keywords:
- C2436
ms.assetid: ca4cc813-bc1d-4c0a-9a2c-3a5fe673d084
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fb7ca7d92a99092e6c0daf63378ff9bff89c4283
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33198696"
---
# <a name="compiler-error-c2436"></a>Derleyici Hatası C2436
'tanımlayıcısı': üye işlevi veya iç içe geçmiş sınıf oluşturucu başlatıcı listesinde  
  
 Üye işlevleri veya yerel sınıflarda oluşturucu başlatıcı listesi başlatılamıyor.  
  
 Aşağıdaki örnek C2436 oluşturur:  
  
```  
// C2436.cpp  
struct S{  
   int f();  
   struct Inner{  
      int i;  
   };  
   S():f(10), Inner(0){}   // C2436  
};  
```