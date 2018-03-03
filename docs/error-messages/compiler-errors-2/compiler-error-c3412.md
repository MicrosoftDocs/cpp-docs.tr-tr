---
title: "Derleyici Hatası C3412 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3412
dev_langs:
- C++
helpviewer_keywords:
- C3412
ms.assetid: aa4dd43b-54ce-4cda-85c1-1a77dd6e34fa
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a4f4716f64e4541ee1f4af7d3c57610a2d6f3843
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3412"></a>Derleyici Hatası C3412
'şablon': geçerli kapsamında şablon specialize olamaz  
  
 Bir şablon sınıfı kapsamında, yalnızca genel veya ad alanı kapsamı özelleştirilmiş olamaz.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C3412 oluşturur.  
  
```  
// C3412.cpp  
template <class T>  
struct S {  
   template <>  
   struct S<int> {};   // C3412 in a class  
};  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, olası bir çözüm gösterir.  
  
```  
// C3412b.cpp  
// compile with: /c  
template <class T>  
struct S {};  
  
template <>  
struct S<int> {};  
```