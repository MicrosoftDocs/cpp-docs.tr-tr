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
ms.openlocfilehash: a9f577f0d353a3baa802973ccf9b036bb68cfc05
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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