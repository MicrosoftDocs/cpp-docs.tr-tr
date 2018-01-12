---
title: "Derleyici Hatası C2380 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2380
dev_langs: C++
helpviewer_keywords: C2380
ms.assetid: 717b1e6e-ddfe-4bac-a5f3-7f9a4dcb1572
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e646a4dcb1e5447b3ae36e740d0228525cb8d4ad
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2380"></a>Derleyici Hatası C2380
'tanımlayıcısı' (oluşturucu dönüş türü veya geçerli sınıf adı geçersiz yeniden tanımlama?) önceki türleri  
  
 Oluşturucu bir değer döndürür veya sınıf adı yeniden tanımlamaktadır.  
  
 Aşağıdaki örnek C2326 oluşturur:  
  
```  
// C2380.cpp  
// compile with: /c  
class C {  
public:  
   int C();   // C2380, specifies an int return  
   int C;   // C2380, redefinition of i  
   C();   // OK  
};  
```