---
title: Derleyici Hatası C2479 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2479
dev_langs:
- C++
helpviewer_keywords:
- C2479
ms.assetid: c74c7869-e65b-4ca1-b6fa-eb39fed4458a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1edd4771e14de4044148d2a6ef93a4516856b064
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33225999"
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