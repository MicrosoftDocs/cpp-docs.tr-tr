---
title: "Derleyici Hatası C2271 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2271
dev_langs: C++
helpviewer_keywords: C2271
ms.assetid: ea47bf57-f55d-4171-8e98-95a71d62820e
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c484a280ab873e4ab7c8ca1dcec492fb59d61869
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2271"></a>Derleyici Hatası C2271
'işleci': yeni/silme resmi listesi değiştiricileri sahip olamaz  
  
 İşleç (`new` veya `delete`) bellek model tanımlayıcısı ile bildirilmedi.  
  
 Aşağıdaki örnek C2271 oluşturur:  
  
```  
// C2271.cpp  
// compile with: /c  
void* operator new(size_t) const {   // C2271  
// try the following line instead  
// void* operator new(size_t) {  
   return 0;  
}  
  
struct X {  
   static void* operator new(size_t) const;   // C2271  
   // try the following line instead  
   // void * X::operator new(size_t) const;   // static member operator new  
};  
```