---
title: "Derleyici Hatası C2299 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2299
dev_langs: C++
helpviewer_keywords: C2299
ms.assetid: d001c2bc-f6fd-47aa-8e42-0eb824d6441d
caps.latest.revision: "16"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8190511605a7f01dc399e1d8a8b4af96477fa407
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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