---
title: "Derleyici Hatası C3769 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3769
dev_langs: C++
helpviewer_keywords: C3769
ms.assetid: 341675e1-7428-4da6-8275-1b2f0a70dacc
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ea13880843f5ca35b8cdda2218f19e5491be504c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3769"></a>Derleyici Hatası C3769
'type': iç içe geçmiş sınıf hemen kapsayan sınıfı aynı ada sahip olamaz  
  
 İç içe geçmiş sınıf hemen kapsayan sınıfı aynı ada sahip olamaz.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C3769 oluşturur.  
  
```  
// C3769.cpp  
// compile with: /c  
class x {  
   class x {};   // C3769  
   class y {  
      class x{};   // OK  
   };  
};  
```