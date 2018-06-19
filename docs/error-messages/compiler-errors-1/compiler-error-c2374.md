---
title: Derleyici Hatası C2374 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2374
dev_langs:
- C++
helpviewer_keywords:
- C2374
ms.assetid: 73b51965-e91c-4e21-9732-f71c1449d22e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dc933b7b47723acc9da025740935a1336ff8fe17
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33224830"
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