---
title: "Derleyici Hatası C2706 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2706
dev_langs: C++
helpviewer_keywords: C2706
ms.assetid: e18da924-c42d-4b09-8e29-f4e0382d7dc6
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 9190c457e5397acbfd8a2358563d2359e9c5190b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2706"></a>Derleyici Hatası C2706
eşleşen olmadan __except geçersiz \__try (eksik '}' içinde \__try blok?)  
  
 Derleme için bir kapanış ayracı bulamadı bir `__try` bloğu.  
  
 Aşağıdaki örnek C2706 oluşturur:  
  
```  
// C2706.cpp  
int main() {  
   __try {  
      void f();  
   // C2706  } missing here  
   __except(GetExceptionCode() == 0x0) {  
   }  
}  
```