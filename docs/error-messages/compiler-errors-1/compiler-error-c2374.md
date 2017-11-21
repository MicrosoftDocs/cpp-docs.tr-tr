---
title: "Derleyici Hatası C2374 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2374
dev_langs: C++
helpviewer_keywords: C2374
ms.assetid: 73b51965-e91c-4e21-9732-f71c1449d22e
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 018f2924aeb59ae58975d41d9147fdfd60c8ee59
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2374"></a>Derleyici Hatası C2374
'tanımlayıcısı': şemadaki; birden çok başlatma  
  
 Tanımlayıcısı birden çok kez başlatılır.  
  
 Aşağıdaki örnek C2374 oluşturur:  
  
```  
// C2374.cpp  
// compile with: /c  
int i = 0;  
int i = 1;   // C2374  
int j = 1;   // OK  
```