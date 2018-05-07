---
title: Derleyici Hatası C2909 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2909
dev_langs:
- C++
helpviewer_keywords:
- C2909
ms.assetid: 1c9df8ae-925d-4002-a5f8-a71413c45f9e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9bb5252c0122f5610348c5fb154fedd1869d131e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2909"></a>Derleyici Hatası C2909
'tanımlayıcısı': işlev şablonunun açık örnekleme dönüş türü gerektirir  
  
 Bir açık örnekleme işlevi şablonu dönüş türüne açık belirtilmesini gerektiriyor. Örtük dönüş türü belirtimi çalışmaz.  
  
 Aşağıdaki örnek C2909 oluşturur:  
  
```  
// C2909.cpp  
// compile with: /c  
template<class T> int f(T);  
template f<int>(int);         // C2909  
template int f<int>(int);   // OK  
```