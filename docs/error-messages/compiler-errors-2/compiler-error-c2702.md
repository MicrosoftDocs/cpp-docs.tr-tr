---
title: "Derleyici Hatası C2702 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2702
dev_langs: C++
helpviewer_keywords: C2702
ms.assetid: 6def15d4-9a8d-43e7-ae35-42d7cb57c27e
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: f95a98262f9c7c00850575af883e4269590ead8e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2702"></a>Derleyici Hatası C2702
__except sonlandırma bloğu içinde görünmeyebilir  
  
 Bir özel durum işleyici (`__try`/`__except`) içine yerleştirilemez bir `__finally` bloğu.  
  
 Aşağıdaki örnek C2702 oluşturur:  
  
```  
// C2702.cpp  
// processor: x86 IPF  
int Counter;  
int main() {  
   __try {}  
   __finally {  
      __try {}   // C2702  
      __except( Counter ) {}   // C2702  
   }  
}  
```