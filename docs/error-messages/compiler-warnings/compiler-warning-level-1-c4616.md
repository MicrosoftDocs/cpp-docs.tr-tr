---
title: "Derleyici Uyarısı (düzey 1) C4616 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4616
dev_langs: C++
helpviewer_keywords: C4616
ms.assetid: 71e15265-c5bc-42ce-a6a9-4879892472b1
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 60e71e087757b105d910434ec4eef4e64740b9b0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4616"></a>Derleyici Uyarısı (düzey 1) C4616
\#pragma uyarısı: uyarı numarası 'number' geçerli derleyici uyarısı  
  
 Belirtilen uyarı numarası [uyarı](../../preprocessor/warning.md) pragma atanamıyor. Pragma yoksayıldı.  
  
 Aşağıdaki örnek C4616 oluşturur:  
  
```  
// C4616.cpp  
// compile with: /W1 /c  
#pragma warning( disable : 0 )   // C4616  
#pragma warning( disable : 999 )   // OK  
#pragma warning( disable : 4998 )   // OK  
```