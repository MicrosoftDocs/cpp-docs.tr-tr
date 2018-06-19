---
title: Derleyici Hatası C3181 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3181
dev_langs:
- C++
helpviewer_keywords:
- C3181
ms.assetid: 5d450f8b-6cef-4452-a0c4-2076e967451d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 33d5c42ce7fec65b2b4481b46590396f3af7d97a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33252169"
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
