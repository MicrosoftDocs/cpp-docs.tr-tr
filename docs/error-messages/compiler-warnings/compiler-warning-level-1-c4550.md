---
title: "Derleyici Uyarısı (düzey 1) C4550 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4550
dev_langs: C++
helpviewer_keywords: C4550
ms.assetid: f902b4ed-5f17-48ea-b693-92f4fb8c8054
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 3b51c657fd94b1b10175e467ff2084665bdb5958
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4550"></a>Derleyici Uyarısı (düzey 1) C4550
bir bağımsız değişken listesi eksik bir işleve ifadeyi hesaplar  
  
 Bir işlev için dereferenced bir işaretçi bir bağımsız değişken listesi eksik.  
  
## <a name="example"></a>Örnek  
  
```  
// C4550.cpp  
// compile with: /W1  
bool f()  
{  
   return true;  
}  
  
typedef bool (*pf_t)();  
  
int main()  
{  
   pf_t pf = f;  
   if (*pf) {}  // C4550  
   return 0;  
}  
```