---
title: "Derleyici Hatası C2785 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2785
dev_langs: C++
helpviewer_keywords: C2785
ms.assetid: d8d13360-0d00-4815-8475-b49c7f0dc0f3
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: a545935e06d958502fb3b97cb8969f92172ca6b6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2785"></a>Derleyici Hatası C2785
'declaration1' ve 'declaration2' farklı dönüş türlerine sahip  
  
 İşlev şablonu uzmanlık dönüş türü birincil işlev şablonunun dönüş türünden farklı.  
  
### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için  
  
1.  Tüm özelleştirmeleri işlevi şablonunun tutarlılığını denetleyin.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C2785 oluşturur:  
  
```  
// C2785.cpp  
// compile with: /c  
template<class T> void f(T);  
  
template<> int f(int); // C2785  
template<> void f(int); // OK  
```