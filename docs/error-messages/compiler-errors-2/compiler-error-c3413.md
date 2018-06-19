---
title: Derleyici Hatası C3413 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3413
dev_langs:
- C++
helpviewer_keywords:
- C3413
ms.assetid: de6c9b05-c373-4bd8-8cb0-12c2cd2e5674
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: afe7d444a755d053dcd73d02cb964510c7ce3324
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33252979"
---
# <a name="compiler-error-c3413"></a>Derleyici Hatası C3413
'name': Geçersiz açık örnekleme  
  
 Derleyici hatalı oluşturulmuş bir açık örnekleme algıladı.  
  
 Aşağıdaki örnek C3413 oluşturur:  
  
```  
// C3413.cpp  
template  
class MyClass {};   // C3413  
```  
  
 Olası çözüm:  
  
```  
// C3413b.cpp  
// compile with: /c  
template <class T>  
class MyClass {};  
  
template <>  
class MyClass<int> {};  
```