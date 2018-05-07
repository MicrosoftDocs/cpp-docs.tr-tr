---
title: Derleyici Hatası C2299 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2299
dev_langs:
- C++
helpviewer_keywords:
- C2299
ms.assetid: d001c2bc-f6fd-47aa-8e42-0eb824d6441d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e21213f08e25050932274a64d0ed56db96f2a453
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2299"></a>Derleyici Hatası C2299
'function': davranış değişikliği: kopya oluşturucu veya kopya atama işleci açık uzmanlık olamaz  
  
 Bu hata için Visual C++ 2005 yapıldığı derleyici uyumluluğu iş sonucunda da oluşturulabilir: önceki sürümlerinde Visual C++, izin verilen açık özelleştirmeleri kopya oluşturucu veya bir kopya atama işleci.  
  
 C2299 gidermek için kopya oluşturucu veya atama işleci bir şablon işlevi, ancak bunun yerine bir sınıf türü isteyen bir şablon olmayan işlevi yapmayın. Şablon bağımsız değişken kaldırmak kopya oluşturucu veya atama işleci açıkça bağımsız şablon belirterek çağıran herhangi bir kod gerekir.  
  
 Aşağıdaki örnek C2299 oluşturur:  
  
```  
// C2299.cpp  
// compile with: /c  
class C {  
   template <class T>  
   C (T t);  
  
   template <> C (const C&);   // C2299  
   C (const C&);   // OK  
};  
```