---
title: "Derleyici Hatası C2479 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2479
dev_langs: C++
helpviewer_keywords: C2479
ms.assetid: c74c7869-e65b-4ca1-b6fa-eb39fed4458a
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: fef1f43a82d039377b3259ae06cd9650a3cc9db4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2479"></a>Derleyici Hatası C2479
'tanımlayıcısı': 'tahsis ()' yalnızca statik kapsam veri öğeleri için geçerlidir  
  
 `__declspec( allocate())` Sözdizimi yalnızca statik verileri için kullanılabilir.  
  
 Aşağıdaki örnek C2479 oluşturur:  
  
```  
// C2479.cpp  
// compile with: /c  
#pragma section("mycode", read)  
static __declspec(allocate("mycode")) void DoNothing() {}   // C2479  
__declspec(allocate("mycode"))  int i = 0;   // OK  
```