---
title: Derleyici Hatası C2351 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2351
dev_langs:
- C++
helpviewer_keywords:
- C2351
ms.assetid: 5439ccf6-66f6-4859-964c-c73f5eddfc1b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1660e5dfc4f17f7617c82eb3e633f345e2774495
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33222387"
---
# <a name="compiler-error-c2351"></a>Derleyici Hatası C2351
artık kullanılmayan C++ oluşturucusu başlatma sözdizimi  
  
 Yalnızca temel sınıfı olsa bile bir oluşturucu için bir stil yeni başlatma listesinde, açıkça doğrudan her temel sınıf adı olmalıdır.  
  
 Aşağıdaki örnek C2351 oluşturur:  
  
```  
// C2351.cpp  
// compile with: /c  
class B {  
public:   
   B() : () {}   // C2351  
   B() {}   // OK  
};  
```