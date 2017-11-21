---
title: "Derleyici Hatası C2267 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2267
dev_langs: C++
helpviewer_keywords: C2267
ms.assetid: ea63bebb-6208-4367-8440-39be07f9c360
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 42385c64119acfb669c7420ad9d3ba18d6daf60b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2267"></a>Derleyici Hatası C2267
'function': blok kapsamlı statik işlevleri geçersiz  
  
 Yerel bir işlev bildirilmiş `static`. Statik işlevler genel kapsama sahip olmalıdır.  
  
 Aşağıdaki örnek C2267 oluşturur:  
  
```  
// C2267.cpp  
static int func2();   // OK  
int main() {  
    static int func1();   // C2267  
}  
```