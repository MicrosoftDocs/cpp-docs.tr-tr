---
title: "Derleyici Hatası C3834 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3834
dev_langs: C++
helpviewer_keywords: C3834
ms.assetid: 059e0dc4-300b-4e74-b6c2-41a57831fe2a
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e586de68a14044ac2907ebbd086bb7469e53a7d1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3834"></a>Derleyici Hatası C3834
Geçersiz açık bir sabitleme işaretçisi cast; sabitlenmiş bir yerel değişken kullanın  
  
 Sabitlenmiş işaretçisi açık atamaları izin verilmiyor.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C3834 oluşturur.  
  
```  
// C3834.cpp  
// compile with: /clr  
int main() {  
   int x = 33;  
  
   pin_ptr<int> p = safe_cast<pin_ptr<int> >(&x);   // C3834  
   pin_ptr<int> p2 = &x;   // OK  
}  
```  
