---
title: "Derleyici Hatası C2823 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2823
dev_langs: C++
helpviewer_keywords: C2823
ms.assetid: 982b1b35-1a7c-456e-b711-f80cfe2d571e
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 84640d17479c27047919016525272ee5a87d178b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2823"></a>Derleyici Hatası C2823  
  
> typedef şablon geçersiz.  
  
İçinde şablonları verilmez `typedef` tanımlar.  
  
## <a name="example"></a>Örnek  
  
Aşağıdaki örnek C2823 oluşturur ve bu düzeltmenin bir yolu gösterir:  
  
```cpp  
// C2823.cpp  
template<class T>  
typedef struct x {  
   T i;   // C2823 can't use T, specify data type and delete template  
   int i;   // OK  
} x1;  
```