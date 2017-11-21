---
title: "Derleyici Hatası C2710 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2710
dev_langs: C++
helpviewer_keywords: C2710
ms.assetid: a2a6bb5b-86ad-4a6c-acd0-e2bef8464e0e
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 5bb6349bf6efb8c63b68c78644343ace5dc07e67
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2710"></a>Derleyici Hatası C2710
'oluşturmak': '__declspec(modifier)' yalnızca bir işaretçi döndüren bir işlev uygulanabilir  
  
 Dönüş değeri olan bir işaretçi bir işlevi olarak yalnızca yapıdır `modifier` uygulanabilir.  
  
 Aşağıdaki örnek C2710 oluşturur:  
  
```  
// C2710.cpp  
__declspec(restrict) void f();   // C2710  
// try the following line instead  
__declspec(restrict) int * g();  
```