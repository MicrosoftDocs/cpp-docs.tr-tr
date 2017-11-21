---
title: "Derleyici Hatası C2159 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2159
dev_langs: C++
helpviewer_keywords: C2159
ms.assetid: 925a2cbd-43c9-45ee-a373-84004350b380
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 06ca0380bbd55d40763fb0fd038de75a0b603842
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2159"></a>Derleyici Hatası C2159
Belirtilen birden fazla depolama sınıfı  
  
 Bir bildirim birden fazla depolama sınıfı içerir.  
  
 Aşağıdaki örnek C2159 oluşturur:  
  
```  
// C2159.cpp  
// compile with: /c  
static int i;   // OK  
extern static int i;   // C2159  
```