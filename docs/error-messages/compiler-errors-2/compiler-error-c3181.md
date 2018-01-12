---
title: "Derleyici Hatası C3181 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3181
dev_langs: C++
helpviewer_keywords: C3181
ms.assetid: 5d450f8b-6cef-4452-a0c4-2076e967451d
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3b083084fab3970d3eecfe846917585bd8ef51df
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3181"></a>Derleyici Hatası C3181
'type': Geçersiz işlecinin işleneni  
  
Geçersiz bir parametre geçildi [TypeID](../../windows/typeid-cpp-component-extensions.md) işleci. Parametresi, bir yönetilen türü olmalıdır.  
  
Derleyici, ortak dil çalışma zamanı türler için eşleme yerel türleri için diğer adlar kullandığına dikkat edin.  
  
Aşağıdaki örnek C3181 oluşturur:  
  
```  
// C3181a.cpp  
// compile with: /clr  
using namespace System;  
  
int main() {  
   Type ^pType1 = interior_ptr<int>::typeid;   // C3181  
   Type ^pType2 = int::typeid;   // OK  
}  
```  
