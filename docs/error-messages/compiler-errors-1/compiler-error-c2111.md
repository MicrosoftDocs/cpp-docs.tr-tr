---
title: "Derleyici Hatası C2111 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2111
dev_langs: C++
helpviewer_keywords: C2111
ms.assetid: 38fd42ec-1480-4a44-aaca-ae4593ed5f50
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 02c2783f156fbdd0c805c0dff71e53a681dc3327
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2111"></a>Derleyici Hatası C2111
'+': işaretçi toplama tam sayı işleneni gerektirir  
  
 Artı kullanarak bir işaretçi nonintegral değer eklemek için girişimde bulunuldu ( `+` ) işleci.  
  
 Aşağıdaki örnek C2111 oluşturur:  
  
```  
// C2111.cpp  
int main() {  
   int *a = 0, *pa = 0, b = 0;  
   double d = 0.00;  
  
   a = pa + d;   // C2111  
   a = pa + b;   // OK  
}  
```